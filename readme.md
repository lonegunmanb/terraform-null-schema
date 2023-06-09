# Terraform Null Provider Schema Repository

This repository contains the generated Go files for the Null provider schemas, which are based on the Terraform Null Provider. These schema files can be used as a reference when writing tools, such as TFLint plugins, that interact with the Null provider.

The internal package from the Terraform Null Provider is not publicly accessible, which is why this repository was created to provide access to the resource schemas.

## Repository Structure

Each tag version of the Terraform Random Provider has a corresponding tag in this repository. You can find the schema files for each provider version under the respective tag.

e.g.: to use `null`'s `3.2.1` schema, you could:

```shell
$ go get github.com/lonegunmanb/terraform-null-schema/v3@v3.2.1
```

Then you can read schemas like this:

```go
import (
"testing"

"github.com/lonegunmanb/terraform-null-schema/v3/generated"
"github.com/stretchr/testify/assert"
)

func TestResourceSchema(t *testing.T) {
assert.NotEmpty(t, generated.Resources)
}
```

## Generating Schema Files

The schema files are generated using the terraform provider schema -json command. This command retrieves the schema information and converts it into JSON format. The JSON files are then converted into Go files, which can be found in this repository.

If you encounter any issues or would like to contribute to this repository, please submit an issue or a pull request on GitHub.

## License

[MIT](LICENSE)
