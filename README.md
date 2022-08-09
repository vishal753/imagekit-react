[<img width="250" alt="ImageKit.io" src="https://raw.githubusercontent.com/imagekit-developer/imagekit-javascript/master/assets/imagekit-light-logo.svg"/>](https://imagekit.io)

# ImageKit.io React SDK

[![Node CI](https://github.com/imagekit-developer/imagekit-react/workflows/Node%20CI/badge.svg)](https://github.com/imagekit-developer/imagekit-react/)
[![npm version](https://img.shields.io/npm/v/imagekitio-react)](https://www.npmjs.com/package/imagekitio-react)
[![codecov](https://codecov.io/gh/imagekit-developer/imagekit-react/branch/master/graph/badge.svg)](https://codecov.io/gh/imagekit-developer/imagekit-react)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Twitter Follow](https://img.shields.io/twitter/follow/imagekitio?label=Follow&style=social)](https://twitter.com/ImagekitIo)

ImageKit React SDK allows you to use real-time [image resizing](https://docs.imagekit.io/features/image-transformations), [optimization](https://docs.imagekit.io/features/image-optimization), and [file uploading](https://docs.imagekit.io/api-reference/upload-file-api/client-side-file-upload) in the client-side.

## Installation

```shell
npm install --save imagekitio-react
```

or

```shell
yarn add imagekitio-react
```

## Usage

### Initialization

Import components in your code:

```js
import { IKImage, IKContext, IKUpload } from 'imagekitio-react'
```

### Quick examples
```js
<IKContext publicKey="your_public_api_key" authenticationEndpoint="https://www.your-server.com/auth">
  // Simple file upload and response handling
  <IKUpload
    onError={onError}
    onSuccess={onSuccess}
    onUpload={onUpload}
  />

  // Passing different upload API options
  <IKUpload
    fileName="file-name.jpg"
    tags={["sample-tag1", "sample-tag2"]}
    customCoordinates={"10,10,10,10"}
    isPrivateFile={false}
    useUniqueFileName={true}
    responseFields={["tags"]}
    folder={"/sample-folder"}
    onError={onError} 
    onSuccess={onSuccess}
    onUpload={onUpload}
  />
</IKContext>
```

## Demo application
* Methods will help you track image upload progress and current status

```js

const onUpload = () => {
    // Start loading, To indicate image upload has started
    setLoading(true)
}

const onSuccess = (res) => {
    // Stop loading, And show successive flow
    setLoading(false)
}

const onError = (err) => {
    // Stop loading, And show error message
    setLoading(false)
    setError(err.message)
}

<IKUpload
    onError={onError}
    onSuccess={onSuccess}
    onUpload={onUpload}
/>
```

## Support

For any feedback or to report any issues or general implementation support, please reach out to [support@imagekit.io](mailto:support@imagekit.io)

## Links
* [Documentation](https://docs.imagekit.io)
* [Main website](https://imagekit.io)

## License
Released under the MIT license.