# Google Text-to-Speech CLI

A simple ruby script for transforming text to speech using the Goolge Text-to-Speech Cloud API.

To use this script you must first setup a account on the Google Cloud Platform and enable the TTS API.
Then create a service account and download the credentials JSON file.
Create a GOOGLE_APPLICATION_CREDENTIALS env variable which points to the credentials JSON file and you're good to go.
Alternatively you can supply the path to the credentials to the script with the `-c` flag.
More info about using the Ruby API client and setting up an account can be found [here](https://cloud.google.com/text-to-speech/docs/reference/libraries#client-libraries-install-ruby).

## Dependencies

Requires `ruby` and the `google-cloud-text_to_speech` gem.

```shell
$ gem install 'google-cloud-text_to_speech'
```

## Usage

```shell
$ echo "Roads? Where we're going we don't need... roads!" | ruby synthesize > out.mp3

# Or stream the output to a media player

$ ruby synthesize input-file | mpv -
```

You can also specify the language and voice.

```shell
$ echo "Dra meg baklengs inn i fuglekassa" | ruby synthesize --lang nb-NO --gender male | mpv -
```
