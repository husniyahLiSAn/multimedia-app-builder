# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Features

In the project website, you can use this feature to :

1. Rename Selected File
2. View Metadata Selected File
3. Download Selected File
4. Delete Selected File
5. View Summary Chart Files

There are new features have been implemented.

### `Upload File`

1. The `handleFileUpload` function is called when the user selects a file through the <input type="file"> element. This function retrieves the selected file using `event.target.files[0]` and then stores it in the selectedFile state using the `setSelectedFile` function. This function is responsible for storing the file to be uploaded.

2. The `setFileUpload` function is called when the user clicks the "Upload" button. This function processes the selected file.

3. In the `setFileUpload` function, we check if there is a selected file (`selectedFile`). If there is, we create an instance of `FileReader` that will be used to read the content of the selected file.

4. In the `reader.onload` section, we define the action to be taken after the file content has finished reading. Here, we create a `metadata` object that contains information about the file to be uploaded, such as `id` (taken from the length of myFiles plus 1), `name` (the name of the selected file), `type` (the file type), and `path` (the location where the file will be uploaded). Then, we update the `myFiles` state by adding the metadata to the array using the spread operator and the `setMyFiles` function. Finally, we display an alert message informing that the file has been uploaded.

5. In the `reader.readAsText` section, we read the content of the selected file as text. If the uploaded file is not a text file, you can use an appropriate method, such as `readAsDataURL` for images.

6. After the upload process is complete, we set `selectedFile` to null using the `setSelectedFile` function, so that the uploaded file is not processed again.

### `Duplicate File`

1. When the button is clicked, this function will be executed. There is a conditional statement to check if `selectedFile` exists or is truthy. This ensures that a file has been selected before proceeding with the duplication process.

2. Inside the conditional statement, a new object `duplicatedFile` is created by spreading the properties of the `selectedFile` object. This allows us to create a shallow copy of the selected file while preserving its properties.

3. Additional properties are modified or added to the `duplicatedFile` object. In this case, the id property is set to `myFiles.length + 1`, which assigns `a new unique ID` for the duplicated file. The `name` property is also modified by appending " - Copy" to the original file name.

4. A new array `newFiles` is created by spreading the elements of the `myFiles` array and adding the `duplicatedFile` object at the end.

5. Finally, the `setMyFiles` function is called with `newFiles` as the argument to update the `myFiles` state with the duplicated file included.

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

The page will reload when you make changes.\
You may also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can't go back!**

If you aren't satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you're on your own.

You don't have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn't feel obligated to use this feature. However we understand that this tool wouldn't be useful if you couldn't customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: [https://facebook.github.io/create-react-app/docs/code-splitting](https://facebook.github.io/create-react-app/docs/code-splitting)

### Analyzing the Bundle Size

This section has moved here: [https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size](https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size)

### Making a Progressive Web App

This section has moved here: [https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app](https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app)

### Advanced Configuration

This section has moved here: [https://facebook.github.io/create-react-app/docs/advanced-configuration](https://facebook.github.io/create-react-app/docs/advanced-configuration)

### Deployment

This section has moved here: [https://facebook.github.io/create-react-app/docs/deployment](https://facebook.github.io/create-react-app/docs/deployment)

### `npm run build` fails to minify

This section has moved here: [https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify](https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify)
