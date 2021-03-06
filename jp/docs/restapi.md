---
Horizon API
---

## getKeypair

```curl
curl -X GET \
  http://localhost:1994/getKeypair \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -H 'postman-token: 87887390-8ad8-1e95-7046-5dbf6076cf89'
```

```jsx
/*react*/
<desc>
Horizon API
</desc>
<script type="text/babel">

  export default class Application extends React.Component {
    callHorizon() {
      fetch('http://localhost:1994/getKeypair')
        .then((response) => response.json())
        .then((responseJSON) => {
            $('#json-renderer').jsonViewer(responseJSON);
            $('#json-renderer').prepend('<p>results:</p>');
        })
        .catch((error) =>{
          $('#json-renderer').jsonViewer(error);
          $('#json-renderer').prepend('<p>results:</p>');
        });
    }

    render() {
      return (
        <div>
          <div className='wrapper' ref={el => this.el = el}>
            <div>
            <button onClick={this.callHorizon.bind(this) }>Run</button>
            </div>
            <pre id="json-renderer">result:</pre>
          </div>
        </div>
      )
    }
  }
```


## createAccount

```curl
curl -X POST \
  http://localhost:1994/createAccount \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -H 'postman-token: f08d110c-c1e6-0fb1-46c9-915ed72f11a1' \
  -d '{
                "secret": "SCMF5DJR4OOJ76N4HNM3Q4UK4UDTM4U5N4IEM7QQI2X2BZ67GO4NMOT5",
                "destination": "GCUWWKSLTP3FANF22BL23N7FG6GLEX4QGKWWD24M6FRMZHT7J6BWNBV3",
                "startingBalance": "25"
            }'
```

```jsx
/*react*/
<desc>
Horizon API
</desc>
<script type="text/babel">

  export default class Application extends React.Component {
    callHorizon() {
      const options = {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({
          "secret": "SCMF5DJR4OOJ76N4HNM3Q4UK4UDTM4U5N4IEM7QQI2X2BZ67GO4NMOT5",
          "destination": keyPair.publicKey(),
          "startingBalance": "20"
        }),
      };

      fetch('http://localhost:1994/createAccount', options)
        .then((response) => response.json())
        .then((responseJSON) => {
            $('#json-renderer-createAccount').jsonViewer(responseJSON);
            $('#json-renderer-createAccount').prepend('<p>results:</p>');
        })
        .catch((error) =>{
          $('#json-renderer-createAccount').jsonViewer(error);
          $('#json-renderer-createAccount').prepend('<p>results:</p>');
        });
    }

    render() {
      return (
        <div>
          <div className='wrapper' ref={el => this.el = el}>
            <div>
            <button onClick={this.callHorizon.bind(this) }>Run</button>
            </div>
            <pre id="json-renderer-createAccount">result:</pre>
          </div>
        </div>
      )
    }
  }
```

## getAccountInfo

```curl
curl -X POST \
  http://localhost:1994/getAccountInfo \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -H 'postman-token: 4499c6ba-778c-92d4-c24c-5430499ea908' \
  -d '{
            "publicKey": "GDRXC5H65UL33R63AP2EBO2XMPH3JSLF7QFEWLBTA4EMCA4WDE6HPE4G"
        }'
```

```jsx
/*react*/
<desc>
Horizon API
</desc>
<script type="text/babel">
  console.log(keyPair.publicKey());
  console.log(keyPair.secret());
  export default class Application extends React.Component {
    callHorizon() {
      const options = {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({
            "publicKey": "GDRXC5H65UL33R63AP2EBO2XMPH3JSLF7QFEWLBTA4EMCA4WDE6HPE4G"
        }),
      };

      fetch('http://localhost:1994/getAccountInfo', options)
        .then((response) => response.json())
        .then((responseJSON) => {
            $('#json-renderer-getAccountInfo').jsonViewer(responseJSON);
            $('#json-renderer-getAccountInfo').prepend('<p>results:</p>');
        })
        .catch((error) =>{
          $('#json-renderer-getAccountInfo').jsonViewer(error);
          $('#json-renderer-getAccountInfo').prepend('<p>results:</p>');
        });
    }

    render() {
      return (
        <div>
          <div className='wrapper' ref={el => this.el = el}>
            <div>
            <button onClick={this.callHorizon.bind(this) }>Run</button>
            </div>
            <pre id="json-renderer-getAccountInfo">result:</pre>
          </div>
        </div>
      )
    }
  }
```

## mergeAccount

```curl
curl -X POST \
  http://localhost:1994/mergeAccount \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -H 'postman-token: 81aa68f7-0bb3-ad8b-579c-970693673e54' \
  -d '{
			"sourceKey": "SAL2RZODFWMCICTUZEKNQ6RGVWMJQDFCQALFMEX2N3EAAIHUL6NVKOTA",
            "destination": "GDRXC5H65UL33R63AP2EBO2XMPH3JSLF7QFEWLBTA4EMCA4WDE6HPE4G"
        }'
```

```jsx
/*react*/
<desc>
Horizon API
</desc>
<script type="text/babel">
  export default class Application extends React.Component {
    callHorizon() {
      const options = {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({
			       "sourceKey": "SAL2RZODFWMCICTUZEKNQ6RGVWMJQDFCQALFMEX2N3EAAIHUL6NVKOTA",
             "destination": "GDRXC5H65UL33R63AP2EBO2XMPH3JSLF7QFEWLBTA4EMCA4WDE6HPE4G"
        }),
      };

      fetch('http://localhost:1994/mergeAccount', options)
        .then((response) => response.json())
        .then((responseJSON) => {
            $('#json-renderer-mergeAccount').jsonViewer(responseJSON);
            $('#json-renderer-mergeAccount').prepend('<p>results:</p>');
        })
        .catch((error) =>{
          $('#json-renderer-mergeAccount').jsonViewer(error);
          $('#json-renderer-mergeAccount').prepend('<p>results:</p>');
        });
    }

    render() {
      return (
        <div>
          <div className='wrapper' ref={el => this.el = el}>
            <div>
            <button onClick={this.callHorizon.bind(this) }>Run</button>
            </div>
            <pre id="json-renderer-mergeAccount">result:</pre>
          </div>
        </div>
      )
    }
  }
```

## setAccountOptions

```curl
curl -X POST \
  http://localhost:1994/setOption \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -H 'postman-token: b3e32283-b000-0803-d3c1-7d1181c4db57' \
  -d '{
				"source_account": "SAL2RZODFWMCICTUZEKNQ6RGVWMJQDFCQALFMEX2N3EAAIHUL6NVKOTA",
				"opts": {}
			}'
```

```jsx
/*react*/
<desc>
Horizon API
</desc>
<script type="text/babel">
  export default class Application extends React.Component {
    callHorizon() {
      const options = {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({
  				"source_account": "SAL2RZODFWMCICTUZEKNQ6RGVWMJQDFCQALFMEX2N3EAAIHUL6NVKOTA",
  				"opts": {}
  			}),
      };

      fetch('http://localhost:1994/setOption', options)
        .then((response) => response.json())
        .then((responseJSON) => {
            $('#json-renderer-setAccountOptions').jsonViewer(responseJSON);
            $('#json-renderer-setAccountOptions').prepend('<p>results:</p>');
        })
        .catch((error) =>{
          $('#json-renderer-setAccountOptions').jsonViewer(error);
          $('#json-renderer-setAccountOptions').prepend('<p>results:</p>');
        });
    }

    render() {
      return (
        <div>
          <div className='wrapper' ref={el => this.el = el}>
            <div>
            <button onClick={this.callHorizon.bind(this) }>Run</button>
            </div>
            <pre id="json-renderer-setAccountOptions">result:</pre>
          </div>
        </div>
      )
    }
  }
```

## findPathPayment

```curl
curl -X POST \
  http://localhost:1994/findPathPayment \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -H 'postman-token: 504a49be-b644-2395-2676-cc83c1648467' \
  -d '{
		   "sourceAccount": "GBGTJZ64L4DBMQX3ZQZZ646CFYRVIQCXTJR2QX4I26FO5EEZAPIQPNX4",
		   "destinationAccount": "GDRXC5H65UL33R63AP2EBO2XMPH3JSLF7QFEWLBTA4EMCA4WDE6HPE4G",
		   "destinationAsset": {
		       "asset_type": "credit_alphanum12",
		       "asset_code": "BAPCOIN",
		       "asset_issuer": "GC5EOK5NFVZUSXUIOAFM6KPIZ2ATV2VD6WZORB3GOSQC3PMKY6KULDDZ"
		   },
		   "destinationAmount": "20"
}'
```

```jsx
/*react*/
<desc>
Horizon API
</desc>
<script type="text/babel">

  export default class Application extends React.Component {
    callHorizon() {
      const options = {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({
      		   "sourceAccount": "GBGTJZ64L4DBMQX3ZQZZ646CFYRVIQCXTJR2QX4I26FO5EEZAPIQPNX4",
      		   "destinationAccount": "GDRXC5H65UL33R63AP2EBO2XMPH3JSLF7QFEWLBTA4EMCA4WDE6HPE4G",
      		   "destinationAsset": {
      		       "asset_type": "credit_alphanum12",
      		       "asset_code": "BAPCOIN",
      		       "asset_issuer": "GC5EOK5NFVZUSXUIOAFM6KPIZ2ATV2VD6WZORB3GOSQC3PMKY6KULDDZ"
      		   },
      		   "destinationAmount": "20"
      }),
      };

      fetch('http://localhost:1994/findPathPayment', options)
        .then((response) => response.json())
        .then((responseJSON) => {
            $('#json-renderer-findPathPayment').jsonViewer(responseJSON);
            $('#json-renderer-findPathPayment').prepend('<p>results:</p>');
        })
        .catch((error) =>{
          $('#json-renderer-findPathPayment').jsonViewer(error);
          $('#json-renderer-findPathPayment').prepend('<p>results:</p>');
        });
    }

    render() {
      return (
        <div>
          <div className='wrapper' ref={el => this.el = el}>
            <div>
            <button onClick={this.callHorizon.bind(this) }>Run</button>
            </div>
            <pre id="json-renderer-findPathPayment">result:</pre>
          </div>
        </div>
      )
    }
  }
```


## pathPayment

```curl
curl -X POST \
  http://localhost:1994/findPathPayment \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -H 'postman-token: 504a49be-b644-2395-2676-cc83c1648467' \
  -d '{
		   "sourceAccount": "GBGTJZ64L4DBMQX3ZQZZ646CFYRVIQCXTJR2QX4I26FO5EEZAPIQPNX4",
		   "destinationAccount": "GDRXC5H65UL33R63AP2EBO2XMPH3JSLF7QFEWLBTA4EMCA4WDE6HPE4G",
		   "destinationAsset": {
		       "asset_type": "credit_alphanum12",
		       "asset_code": "BAPCOIN",
		       "asset_issuer": "GC5EOK5NFVZUSXUIOAFM6KPIZ2ATV2VD6WZORB3GOSQC3PMKY6KULDDZ"
		   },
		   "destinationAmount": "20"
}'
```

```jsx
/*react*/
<desc>
Horizon API
</desc>
<script type="text/babel">

  export default class Application extends React.Component {
    callHorizon() {
      const options = {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({
    			"sourceKey": "SCMF5DJR4OOJ76N4HNM3Q4UK4UDTM4U5N4IEM7QQI2X2BZ67GO4NMOT5",
    			"destination": "GBGTJZ64L4DBMQX3ZQZZ646CFYRVIQCXTJR2QX4I26FO5EEZAPIQPNX4",
    			"sourceAsset": {
    				"asset_type": "credit_alphanum12",
    				"asset_code": "BAPCOIN",
    				"asset_issuer": "GC5EOK5NFVZUSXUIOAFM6KPIZ2ATV2VD6WZORB3GOSQC3PMKY6KULDDZ"
    			},
    			"sourceMax": "1",
    			"path": [],
    			"destAsset": {
    				"asset_type": "credit_alphanum12",
    				"asset_code": "TUANCOIN",
    				"asset_issuer": "GAX5OPBPGWF6MRF7Q43AGYPBY4N5JWOF2ZEZSQVCB2UEXEOPJ3FKUSBS"
    			},
    			"destAmount": "1"
    		}),
      };

      fetch('http://localhost:1994/pathPayment', options)
        .then((response) => response.json())
        .then((responseJSON) => {
            $('#json-renderer-pathPayment').jsonViewer(responseJSON);
            $('#json-renderer-pathPayment').prepend('<p>results:</p>');
        })
        .catch((error) =>{
          $('#json-renderer-pathPayment').jsonViewer(error);
          $('#json-renderer-pathPayment').prepend('<p>results:</p>');
        });
    }

    render() {
      return (
        <div>
          <div className='wrapper' ref={el => this.el = el}>
            <div>
            <button onClick={this.callHorizon.bind(this) }>Run</button>
            </div>
            <pre id="json-renderer-pathPayment">result:</pre>
          </div>
        </div>
      )
    }
  }
```

## changeTrust

```curl
curl -X POST \
  http://localhost:1994/changeTrust \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -H 'postman-token: aacd1f8c-d68e-a22b-1616-1cc0222f0ebf' \
  -d '{
                "secrectKey": "SCMF5DJR4OOJ76N4HNM3Q4UK4UDTM4U5N4IEM7QQI2X2BZ67GO4NMOT5",
                "assetCode": "TEST4",
                "assetIssuer": "GC5LVEZ2TVZNQI2S4XUQU65VJU2475CBIHOU6XF3MHUJDB63AWZLKAD7",
                "limit": "0"
            }'
```

```jsx
/*react*/
<desc>
Horizon API
</desc>
<script type="text/babel">

  export default class Application extends React.Component {
    callHorizon() {
      const options = {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({
                "secrectKey": "SCMF5DJR4OOJ76N4HNM3Q4UK4UDTM4U5N4IEM7QQI2X2BZ67GO4NMOT5",
                "assetCode": "TEST4",
                "assetIssuer": "GC5LVEZ2TVZNQI2S4XUQU65VJU2475CBIHOU6XF3MHUJDB63AWZLKAD7",
                "limit": "0"
            }),
      };

      fetch('http://localhost:1994/changeTrust', options)
        .then((response) => response.json())
        .then((responseJSON) => {
            $('#json-renderer-changeTrust').jsonViewer(responseJSON);
            $('#json-renderer-changeTrust').prepend('<p>results:</p>');
        })
        .catch((error) =>{
          $('#json-renderer-changeTrust').jsonViewer(error);
          $('#json-renderer-changeTrust').prepend('<p>results:</p>');
        });
    }

    render() {
      return (
        <div>
          <div className='wrapper' ref={el => this.el = el}>
            <div>
            <button onClick={this.callHorizon.bind(this) }>Run</button>
            </div>
            <pre id="json-renderer-changeTrust">result:</pre>
          </div>
        </div>
      )
    }
  }
```

## payment

```curl
curl -X POST \
  http://localhost:1994/payment \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -H 'postman-token: fb0b07ea-363b-7ffb-ce64-ada89314ac82' \
  -d '{
		   "sourceKey": "SCMF5DJR4OOJ76N4HNM3Q4UK4UDTM4U5N4IEM7QQI2X2BZ67GO4NMOT5",
		   "destination": "GBGTJZ64L4DBMQX3ZQZZ646CFYRVIQCXTJR2QX4I26FO5EEZAPIQPNX4",
		   "asset":{
				"asset_type": "credit_alphanum12",
    			"asset_code": "BAPCOIN",
    			"asset_issuer": "GC5EOK5NFVZUSXUIOAFM6KPIZ2ATV2VD6WZORB3GOSQC3PMKY6KULDDZ"
		   },
		   "amount": "1"
		 }'
```

```jsx
/*react*/
<desc>
Horizon API
</desc>
<script type="text/babel">

  export default class Application extends React.Component {
    callHorizon() {
      const options = {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({
  		   "sourceSecret": "SCMF5DJR4OOJ76N4HNM3Q4UK4UDTM4U5N4IEM7QQI2X2BZ67GO4NMOT5",
  		   "destination": "GBGTJZ64L4DBMQX3ZQZZ646CFYRVIQCXTJR2QX4I26FO5EEZAPIQPNX4",
  		   "asset":{
  				  "asset_type": "credit_alphanum12",
      			"asset_code": "ACB",
      			"asset_issuer": "GBGTJZ64L4DBMQX3ZQZZ646CFYRVIQCXTJR2QX4I26FO5EEZAPIQPNX4"
  		   },
  		   "amount": "1"
  		 }),
      };

      fetch('http://localhost:1994/payment', options)
        .then((response) => response.json())
        .then((responseJSON) => {
            $('#json-renderer-payment').jsonViewer(responseJSON);
            $('#json-renderer-payment').prepend('<p>results:</p>');
        })
        .catch((error) =>{
          $('#json-renderer-payment').jsonViewer(error);
          $('#json-renderer-payment').prepend('<p>results:</p>');
        });
    }

    render() {
      return (
        <div>
          <div className='wrapper' ref={el => this.el = el}>
            <div>
            <button onClick={this.callHorizon.bind(this) }>Run</button>
            </div>
            <pre id="json-renderer-payment">result:</pre>
          </div>
        </div>
      )
    }
  }
```

## submitTransaction

```curl
curl -X POST \
  http://localhost:1994/transactions \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -H 'postman-token: 93efad50-87dc-8cfe-0f0e-f32e80bd7aa3' \
  -d '{
  	"tx": "AAAAAGwn8ekiKwVX8I/GUc63zte5/Pj8fKR6aXdYolDaZHmCAAAnEAAEHCcAAABRAAAAAAAAAAEAAAANSVNTVUlOR19BU1NFVAAAAAAAAAEAAAAAAAAAAQAAAAC6upM6nXLYI1Ll6Qp7tU01z/RBQd1PXLth6JGH2wWytQAAAAJURVNUMjQAAAAAAAAAAAAAbCfx6SIrBVfwj8ZRzrfO17n8+Px8pHppd1iiUNpkeYIAAAAAAJiWgAAAAAAAAAAB2mR5ggAAAEBvPapD13qTDXKA5NXQfizakkDtxR+s5USIvtuNvbi/xKgUp5XxDjpcqDZNSEc3bI3yj90yh36rE1xyHhOaXUcM"
  }'
```

```jsx
/*react*/
<desc>
Horizon API
</desc>
<script type="text/babel">

  export default class Application extends React.Component {
    callHorizon() {
      const options = {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({
        	"tx": "AAAAAGwn8ekiKwVX8I/GUc63zte5/Pj8fKR6aXdYolDaZHmCAAAnEAAEHCcAAABRAAAAAAAAAAEAAAANSVNTVUlOR19BU1NFVAAAAAAAAAEAAAAAAAAAAQAAAAC6upM6nXLYI1Ll6Qp7tU01z/RBQd1PXLth6JGH2wWytQAAAAJURVNUMjQAAAAAAAAAAAAAbCfx6SIrBVfwj8ZRzrfO17n8+Px8pHppd1iiUNpkeYIAAAAAAJiWgAAAAAAAAAAB2mR5ggAAAEBvPapD13qTDXKA5NXQfizakkDtxR+s5USIvtuNvbi/xKgUp5XxDjpcqDZNSEc3bI3yj90yh36rE1xyHhOaXUcM"
        }),
      };

      fetch('http://localhost:1994/transactions', options)
        .then((response) => response.json())
        .then((responseJSON) => {
            $('#json-renderer-submitTransaction').jsonViewer(responseJSON);
            $('#json-renderer-submitTransaction').prepend('<p>results:</p>');
        })
        .catch((error) =>{
          $('#json-renderer-submitTransaction').jsonViewer(error);
          $('#json-renderer-submitTransaction').prepend('<p>results:</p>');
        });
    }

    render() {
      return (
        <div>
          <div className='wrapper' ref={el => this.el = el}>
            <div>
            <button onClick={this.callHorizon.bind(this) }>Run</button>
            </div>
            <pre id="json-renderer-submitTransaction">result:</pre>
          </div>
        </div>
      )
    }
  }
```
