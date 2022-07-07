# react-custom-modal

This component supports showing any custom modal dialog.

It is possible to display by method call.

[Example](https://sk39.github.io/react-custom-modal/)

> 

[![NPM](https://img.shields.io/npm/v/react-custom-modal.svg)](https://www.npmjs.com/package/react-custom-modal) 

## Install

```bash
npm install react-custom-modal
```


## Usage
```jsx
import React, {Component} from 'react'
import 'react-custom-modal/dist/index.css'
import Modal from 'react-custom-modal'

export default class App extends Component {
  constructor(props) {
    super(props)
    this.dialog = React.createRef()
    this.showDialog = this.showDialog.bind(this)
  }

  showDialog() {
    this.dialog.current.show({
      component: <CustomDialog/>,
      animation: 'slideUp'
    })
  }

  render() {
    return (
      <div>
        <button className='btn'
                onClick={this.showDialog}>
          Show Dialog
        </button>
        <Modal className='Custom'
               dialogClass='CustomDialog'
               ref={this.dialog}/>
      </div>
    )
  }
}

class CustomDialog extends Component {
  render() {
    const {close} = this.props
    return (
      <div>
        <div className='modal-header'>
          <span className='title'>Modal title</span>
          <button className='close-btn' onClick={close}>
            <span>&times;</span>
          </button>
        </div>
        <div className='modal-body'>
          <p>Modal body text goes here.</p>
        </div>
        <div className='modal-footer'>
          <button className='btn' onClick={close}>Cancel</button>
          <button className='btn' onClick={close}>Save</button>
        </div>
      </div>
    )
  }
}
```

## License

MIT © [sk39](https://github.com/sk39)
