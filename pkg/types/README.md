# types
--
    import "github.com/computes/go-sdk/pkg/types"


## Usage

#### type Condition

```go
type Condition struct {
	Name           string               `json:"name,omitempty"`
	Condition      string               `json:"condition"`
	TaskDefinition *POLYMORPH.Polymorph `json:"taskDefinition"`
	Action         string               `json:"action,omitempty"`
	Source         *DatasetLink         `json:"source"`
}
```

Condition represents a condition

#### type DatasetLink

```go
type DatasetLink struct {
	Dataset *POLYMORPH.Polymorph `json:"dataset"`
	Path    string               `json:"path,omitempty"`
}
```

DatasetLink represents a dataset link with path

#### type Runner

```go
type Runner struct {
	Metadata json.RawMessage `json:"metadata"`
	Type     string          `json:"type"`
}
```

Runner represents how a task should run

#### type Task

```go
type Task struct {
	Input          *DatasetLink         `json:"input"`
	TaskDefinition *POLYMORPH.Polymorph `json:"taskDefinition"`
	Status         *POLYMORPH.Polymorph `json:"status"`
}
```

Task represents a task

#### type TaskDefinition

```go
type TaskDefinition struct {
	Conditions []Condition           `json:"conditions,omitempty"`
	Result     *TaskDefinitionResult `json:"result"`
	Runner     *Runner               `json:"runner"`
}
```

TaskDefinition represents a task definition

#### type TaskDefinitionResult

```go
type TaskDefinitionResult struct {
	Action      string       `json:"action,omitempty"`
	Destination *DatasetLink `json:"destination"`
}
```

TaskDefinitionResult represents a task definition result