
<script lang="ts">
	import { createWallet, KinClient, KinTest, Wallet } from '@kin-sdk/client';

	const client = new KinClient(KinTest)
	const account: Wallet = createWallet('create', { name: 'Account 1' })

	const destination = 'Don8L4DTVrUrRAcVTsFoCRqei5Mokde3CV3K9Ut4nAGZ'
	let step1: string;
	let step2: string;
	let step3: string;
	let step4: string;

	async function create() {
      const [result, error] = await client.createAccount(account.secret!)
      if (error) {
        console.error(error)
      } else {
        console.log(result)
        step1 = pretty(result);
      }
    }

	async function resolve() {
      const [result, error] = await client.getBalances(account.publicKey!)
      if (error) {
        console.error(error)
      } else {
        console.log(result)
        step2 = pretty(result);
      }
    }

    async function airdrop() {
      const [result, error] = await client.requestAirdrop(account.publicKey!, '1000')
      if (error) {
        console.error(error)
      } else {
        console.log(result)
        step3 = pretty(result);
      }
    }
	async function sendKin() {
      const [result, error] = await client.submitPayment({
        secret: account.secret!,
        tokenAccount: account.publicKey!,
        amount: '10',
        destination,
        memo: 'One Kin for Donald',
      })
      if (error) {
        console.error(error)
      } else {
        console.log(result)
        step4 = pretty(result);
      }

    }

	async function pretty(value : any) {
      if(!Object.keys(value).length) return "";
      return JSON.stringify(value, null, 2);
    }
</script>

<div>
    <div class="hello">Testing Kin</div>
    <div>
      <button on:click={create}>Create</button>
      <pre>{{ step1 }}</pre>
    </div>
    <div>
      <button on:click={resolve}>Resolve</button>
      <pre>{{ step2 }}</pre>
    </div>
    <div>
      <button on:click={airdrop}>Airdrop</button>
      <pre>{{ step3 }}</pre>
    </div>
    <div>
      <button on:click={sendKin}>Send</button>
      <pre>{{ step4 }}</pre>
    </div>
</div>

<style>
	
</style>