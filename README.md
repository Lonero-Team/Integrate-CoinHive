# Integrate-CoinHive
CoinHive configuration for LNR  
```
const CoinHive = require('coin-hive');
(async () => {
  const miner = await CoinHive('<YOUR-LONERO-ADDRESS>', {
    pool: {
      Host = '142.93.171.115,
      Port = 34414,
      pass: '<YOUR-PASSWORD-FOR-POOL>' // default 'x' if not provided
    }
  });
  await miner.start();
  miner.on('found', () => console.log('Found!'));
  miner.on('accepted', () => console.log('Accepted!'));
  miner.on('update', data =>
    console.log(`
    Hashes per second: ${data.hashesPerSecond}
    Total hashes: ${data.totalHashes}
    Accepted hashes: ${data.acceptedHashes}
  `)
  );
})();
```
### Command
```
coin-hive <YOUR-LONERO-ADDRESS> --pool-host=142.93.171.115 --pool-port=3333 --pool-pass=<YOUR-PASSWORD-FOR-POOL>
```
