# Foundations

# 01: Tensors

## Basic Constructors 

**Read-only** properties exposed by the Tensor class:

| Property | Type | Description |   
| --- | --- | --- |
| shape | tuple | Dimensions, e.g., (2, 3) |
| data | np.ndarray | Underlying NumPy array |
| size | int | Total number of elements | 
| dtype | np.dtype | Data type (float32) |

Arithmetic dunder methods and their Python operator equivalents:

| Operation	| Method | Example |
| --- | --- | --- |
| Addition | `__add__` | x + y or x + 2 |
| Subtraction | `__sub__` | x - y |
| Multiplication | `__mul__` | x * y |
| Division | `__truediv__` | x / y |


## Ranks 

Tensor ranks:

| Rank | Name | Shape | Concrete Example |
| --- | --- | --- | --- |
| 0D | Scalar | () | Temperature reading: 72.5 |
| 1D | Vector | (768,) | Audio sample: 768 measurements |
| 2D | Matrix | (128, 768) | Spreadsheet: 128 rows × 768 columns |
| 3D | 3D Tensor | (32, 224, 224) | Video frames: 32 grayscale images |
| 4D | 4D Tensor | (32, 3, 224, 224) | Video frames: 32 color (RGB) images |



## Broadcasting

Broadcasting in NumPy is a powerful mechanism that allows arithmetic operations to be performed on arrays of different shapes and sizes. Instead of manually reshaping our data or using slow Python loops, NumPy automatically "stretches" or duplicates the smaller array across the larger one so they have compatible shapes. 

Take an example:

![broadcasting_example](https://mlsysbook.ai/tinytorch/assets/images/diagrams/01_tensor-diag-2.svg)


Broadcasting compatibility for representative shape pairs.

| Shape A |	Shape B | Result | Valid? |
| --- | --- | --- | --- |
| (3, 4) | (4,)	| (3, 4) | ✓ |
| (3, 4) | (3, 1) | (3, 4) | ✓ | 
| (3, 4) | (3,) | Error | ✗ (3 ≠ 4) | 
| (2, 3, 4) | (3, 4) | (2, 3, 4) | ✓ |