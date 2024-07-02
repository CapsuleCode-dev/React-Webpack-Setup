This is a [webpack](https://webpack.js.org/) project with React.

## Reqiurements 
- [nodejs](https://nodejs.org/en) v20.15.0
- [npm](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm) v10.2.4


## install of all Dependencies

```
npm init -y
npm i react react-dom
npm i -D @babel/core @babel/preset-env @babel/preset-react babel-loader file-loader style-loader css-loader sass-loader sass webpack-dev-server webpack webpack-cli
```
## Babel Configaration 
Create a Babel configuration file named '.babelrc' and copy and paste the below code into this file.ss
```
{
    "presets": ["@babel/preset-env", "@babel/preset-react"]
}
```
## Webpack configuration file
Finally, create a webpack configuration file named 'webpack.config.js' and copy and paste the below code into this file.
```
module.exports = {
    output: {
        path: path.join(__dirname, '/dist'),
        filename: 'index.bundle.js',
    },
    devServer: {
        port: 3010,
        static: {
            directory: path.join(__dirname, 'dist'),
          },
        hot: true,

    },
    module: {
        rules: [
            {
                test: /\.(js|jsx)$/,
                exclude: /node_modules/,
                use: {
                    loader: 'babel-loader'
                }
            },
            {
                test: /\.scss$/,
                use: [ 
                    'css-loader',
                    'sass-loader',
                ],
            }
        ]
    }, 
};
```
## Deploy  
```
npm run build
npm run serve
```
