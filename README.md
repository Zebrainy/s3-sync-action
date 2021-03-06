# Upload to AWS S3 or Download from S3

## Usage

if you want to upload files:

```yml
        - uses: actions/checkout@v2
          # Make changes here
        - name: Sync with AWS (UPLOAD)
          uses: Zebrainy/s3-sync-action@v1
          with:
            dirname: build/dir
            bucketname: my-bucket
            s3dirname: selectel-folder
            AWS_KEY_ID: ${{ secrets.AWS_KEY_ID }}
            AWS_ACCESS_KEY: ${{ secrets.AWS_ACCESS_KEY }}
```

if you want to download files:

```yml
        - uses: actions/checkout@v2
          # Make changes here
        - name: Sync with AWS (DOWNLOAD)
          uses: Zebrainy/s3-sync-action@v1
          with:
            dirname: download-dir
            bucketname: my-bucket
            s3dirname: selectel-folder
            DOWNLOAD: true
            AWS_KEY_ID: ${{ secrets.AWS_KEY_ID }}
            AWS_ACCESS_KEY: ${{ secrets.AWS_ACCESS_KEY }}
```

if you want to download a sinlge file:
```yml
            s3dirname: selectel/folder/from
            FILENAME: my-build.zip
            DOWNLOAD: true
            dirname: download/to/dir
```

### Action inputs

| Name | Description | Required | Default |
| --- | --- | --- | --- |
| `dirname` | Folder to upload. | `Yes` | `-` |
| `s3dirname` | Folder on S3(Simple Storage Service) to upload to. | `Yes` | `-` |
| `bucketname` | Bucket/container name. containers | `Yes` | `-` |
| `AWS_KEY_ID` | AWS id. | `Yes` | `-` |
| `AWS_ACCESS_KEY` | AWS access key. | `Yes` | `-` |
| `REGION` | If you need another region. | `No` | `us-east-2` |
| `DOWNLOAD` | If want to download a file. (`true`/`false`) | `No` | `false` |
| `FILENAME` | If want to download a single file. (`filename`) | `No` | `-` |

