<div align="center">
  📦
</div>
<h1 align="center">
  action-upload-diawi
</h1>

<p align="center">
   A GitHub Action for uploading APK to Diawi
</p>

<div align="center">
  <a href="https://github.com/rnkdsh/action-upload-diawi/actions">
		<img src="https://github.com/rnkdsh/action-upload-diawi/workflows/Main/badge.svg"/>
	</a>
</div>

<br />

## Inputs

| Name                         | Type    | Description                                                                                                                              |
| ---------------------------- | ------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| `token`                      | String  | Diawi API access token                                                                                                                   |
| `file`                       | File    | APK file to upload on Diawi                                                                                                              |
| `password`                   | String  | Protect your app with a password. It will be required to access the installation page                                                    |
| `recipients`                 | String  | Email addresses Diawi will send the result to (up to 5 separated by commas for starter/premium/enterprise accounts, 1 for free accounts) |
| `wall_of_apps`               | Boolean | Allow Diawi to display the app's icon on the wall of apps                                                                                |
| `find_by_udid`               | Boolean | Allow your testers to find the app on Diawi\'s mobile web app using their UDID (iOS only)                                                |
| `installation_notifications` | Boolean | Receive notifications each time someone installs the app (only starter/premium/enterprise accounts)                                      |
| `dry-run`                    | Boolean | Only parse the arguments without executing the upload                                                                                    |
| `comment`                    | String  | Additional information to your users on this build: the comment will be displayed on the installation page                               |

## Outputs

| Name  | Type   | Description            |
| ----- | ------ | ---------------------- |
| `url` | String | URL generated by Diawi |

## Environment Variables

The following are _required_ as `step.env` keys

| Name           | Description                           |
| -------------- | ------------------------------------- |
| `GITHUB_TOKEN` | GITHUB_TOKEN as provided by `secrets` |
| `DIAWI_TOKEN`  | API token generated from Diawi        |

## Example

```yaml
uses: rnkdsh/action-upload-diawi@v1.1.1
with:
  token: ${{ secrets.DIAWI_TOKEN }}
  file: ./example.apk
```
