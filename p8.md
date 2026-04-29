const fs = require('fs');
const path = './'; // folder to read

const items = fs.readdirSync(path, { withFileTypes: true });

const result = items.map(item => ({
  name: item.name,
  type: item.isDirectory() ? 'directory' : 'file'
}));

console.log(JSON.stringify(result, null, 2));