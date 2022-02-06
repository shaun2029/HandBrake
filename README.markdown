# Hack to force hard CBR for streaming
The main HandBreak project does not produce constant bitrate H264 that satisfies my streaming needs.
This fork overrides some parameters to improve CBR performance, only when Hanbrake is set to use CBR.

    param.i_keyint_min *= 3;                          //Keyint to fps x 3
    param.i_keyint_max = param.i_keyint_min;
    param.i_scenecut_threshold = 0;
    param.i_nal_hrd = X264_NAL_HRD_CBR;               // Hard CBR
    param.rc.i_vbv_max_bitrate = job->vbitrate;       // Set to average bitrate
    param.rc.i_vbv_buffer_size = job->vbitrate * 2;   // Set to 2 x bitrate
    param.rc.i_lookahead = param.i_keyint_min;        // Lookahead set to 3 x fps


# HandBrake [![macOS Build](https://github.com/HandBrake/HandBrake/workflows/macOS%20build/badge.svg)](https://github.com/HandBrake/HandBrake/actions?query=workflow%3A%22macOS+build%22) [![Windows Build](https://github.com/HandBrake/HandBrake/workflows/Windows%20Build/badge.svg)](https://github.com/HandBrake/HandBrake/actions?query=workflow%3A%22Windows+Build%22) [![Linux Build](https://github.com/HandBrake/HandBrake/workflows/Linux%20Build/badge.svg)](https://github.com/HandBrake/HandBrake/actions?query=workflow%3A%22Linux+Build%22)

HandBrake is an open-source video transcoder available for Linux, Mac, and Windows, licensed under the [GNU General Public License (GPL) Version 2](LICENSE).

HandBrake takes videos you already have and makes new ones that work on your mobile phone, tablet, TV media player, game console, computer, or web browser—nearly anything that supports modern video formats.

HandBrake works with most common video files and formats, including ones created by consumer and professional video cameras, mobile devices such as phones and tablets, game and computer screen recordings, and DVD and Blu-ray discs. HandBrake leverages tools such as FFmpeg, x264, and x265 to create new MP4 or MKV video files from these *Sources*.

For information on downloading, building/installing, and using HandBrake, see the official [HandBrake Documentation](https://handbrake.fr/docs).


## Community Support

Visit the [HandBrake Community Forums](https://forum.handbrake.fr/).

For information on HandBrake's community support channels, please see [Community Support](https://handbrake.fr/docs/en/latest/help/community-support.html).

Our [community rules](https://forum.handbrake.fr/app.php/rules) and [code of conduct](https://github.com/HandBrake/HandBrake/blob/master/CODE_OF_CONDUCT.md) apply to both our site and GitHub.


## Contributing

We welcome most contributions. While it is our goal to allow everyone to contribute, contributions not meeting the project's goals or  standards may be rejected.

Please read our [guide to contributing](https://handbrake.fr/docs/en/latest/contributing/contribute.html). This will provide you with all the information you need to start contributing to the project. 

## Translations

We are now accepting translations via  [Transifex](https://www.transifex.com/HandBrakeProject/public) 

Please read our [Translations Guide](https://github.com/HandBrake/HandBrake/blob/master/TRANSLATION.markdown) and follow the instructions if you are interested in joining the translation effort.


## Additional Information

[Authors](AUTHORS.markdown)  
[License](LICENSE)  
[News](NEWS.markdown)  

## Special Thanks

<a href="https://www.macstadium.com/"><img width="200" alt="MacStadium" src="https://uploads-ssl.webflow.com/5ac3c046c82724970fc60918/5c019d917bba312af7553b49_MacStadium-developerlogo.png"></a>

and to many others who have contributed! [Thanks](THANKS.markdown)
