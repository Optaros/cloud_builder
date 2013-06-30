# CloudBuilder

Generates JSON config for AWS CloudFormation using a Ruby DSL.

Based on https://github.com/songkick/cloud_formatter 

## Installation

Clone the repository, then run:
	gem build cloud_builder.gemspec
	gem install cloud_builder-version.gem

## Usage

    $ stack --help
    Usage:
        stack [OPTIONS] STACK

    Parameters:
        STACK                         stack to build

    Options:
        -r, --region REGION           AWS region to use (default: $EC2_REGION, or "us-east-1")
        -v, --validate                validate the stack file before doing anything else
        -b, --bucket BUCKET           upload template to BUCKET (default: $CLOUD_BUILDER_BUCKET, or nil)
        -t, --diff-tool DIFF_TOOL     tool to use for diff (default: $CLOUD_BUILDER_DIFF_TOOL)
        -c, --create                  create the stack
        -u, --update                  update the stack
        -d, --diff                    do a diff between the existing template in BUCKET and the generated template
        -e, --estimate                estimate template cost
        -h, --help                    print help

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

## Changelog

### 0.0.6
- added support for template Outputs (see http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/outputs-section-structure.html)

### 0.0.5
- cli can use the EC2_REGION, CLOUD_BUILDER_BUCKET and CLOUD_BUILDER_DIFF_TOOL environment variables as defaults for --region, --bucket and --diff-tool
- deprecated the --upload flag/action, if you specify a bucket the stack json is uploaded by default

### 0.0.4
- support for specifying an AWS region

### 0.0.3
- add the Changelog
- AWS resources can have a Version property

### 0.0.2
- fix cloud_builder problem when using --help
- add DontFormatUnderscore class
- estimation should be done after uploading to s3 bucket
- add --diff-tool to specify a different tool to use for diffs

### 0.0.1 
- beta initial release