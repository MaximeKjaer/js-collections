# State of JavaScript iterable collections

The following document keeps track of the available methods on JavaScript collections. This is still very much an early draft, and may contain errors! Further work is needed to explain why some methods don't make sense, rule more methods out, and add links to relevant MDN documentation or TC39 proposals.

**Legend**:

- ✅ means that there is specification for this
- 🚀 means that there is a proposal for this
- ❓  means that the feature *may* make sense, but no proposal exists
- 🚧 means that the feature doesn't make sense
- 👴 means that the feature has been deprecated

## Modification

|                   |                     Array                     | **Set** | **Map** | IterableIterator |
| ----------------- | :-------------------------------------------: | :-----: | :-----: | :--------------: |
| `concat`, `union` |                       ✅                       |    ❓    |    ❓    |        ❓         |
| `dropWhile`       |                       ❓                       |    🚧    |    🚧    |        ❓         |
| `filter`          |                       ✅                       |    ❓    |    ❓    |        ❓         |
| `flatMap`         | [🚀](https://github.com/tc39/proposal-flatMap) |    ❓    |    ❓    |        ❓         |
| `flatten`         | [🚀](https://github.com/tc39/proposal-flatMap) |    ❓    |    ❓    |        ❓         |
| `intersection`    |                       ❓                       |    ❓    |    ❓    |        ❓         |
| `map`             |                       ✅                       |    ❓    |    ❓    |        ❓         |
| `takeWhile`       |                       ❓                       |    ❓    |    ❓    |        ❓         |
| `unique`          |                       ❓                       |    🚧    |    ❓    |        ❓         |
## Reduction

|                   | Array | **Set** | **Map** | IterableIterator |
| ----------------- | :---: | :-----: | :-----: | :--------------: |
| `every`           |   ✅   |    ❓    |    ❓    |        ❓         |
| `find`            |   ✅   |    ❓    |    ❓    |        ❓         |
| `findIndex`       |   ✅   |    ❓    |    ❓    |        ❓         |
| `includes`, `has` |   ✅   |    ✅    |    ✅    |        ❓         |
| `join`            |   ✅   |    ❓    |    ❓    |        ❓         |
| `max`             |   ❓   |    ❓    |    ❓    |        ❓         |
| `min`             |   ❓   |    ❓    |    ❓    |        ❓         |
| `reduce`          |   ✅   |    ❓    |    ❓    |        ❓         |
| `reduceRight`     |   ✅   |    🚧    |    🚧    |        ❓         |
| `some`            |   ✅   |    ❓    |    ❓    |        ❓         |
| `sum`             |   ❓   |    ❓    |    🚧    |        ❓         |

## Comparison

|              | Array | **Set** | **Map** | IterableIterator |
| ------------ | :---: | :-----: | :-----: | :--------------: |
| `disjoint`   |   ❓   |    ❓    |    ❓    |        ❓         |
| `equals`     |   ❓   |    ❓    |    ❓    |        ❓         |
| `intersects` |   ❓   |    ❓    |    ❓    |        ❓         |

## Reorganization

|           | Array | **Set** | **Map** | IterableIterator |
| --------- | :---: | :-----: | :-----: | :--------------: |
| `chunks`  |   ❓   |    ❓    |    ❓    |        ❓         |
| `shuffle` |   ❓   |    🚧    |    🚧    |        ❓         |
| `slice`   |   ✅   |    🚧    |    🚧    |        ❓         |
| `unzip`   |   ❓   |    ❓    |    🚧    |        ❓         |
| `zip`     |   ❓   |    ❓    |    🚧    |        ❓         |

## Construction

|         |                            Array                             |                       **Set**                       |                       **Map**                       | IterableIterator |
| ------- | :----------------------------------------------------------: | :-------------------------------------------------: | :-------------------------------------------------: | :--------------: |
| `fill`  |                              ✅                               |                          ❓                          |                          ❓                          |        ❓         |
| `from`  | [✅](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/from) | [🚀](https://github.com/tc39/proposal-setmap-offrom) | [🚀](https://github.com/tc39/proposal-setmap-offrom) |        ❓         |
| `of`    | [✅](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/of) | [🚀](https://github.com/tc39/proposal-setmap-offrom) | [🚀](https://github.com/tc39/proposal-setmap-offrom) |        ❓         |
| `range` |                              ❓                               |                          ❓                          |                          🚧                          |        ❓         |

## Iteration

|              | Array | **Set** | **Map** | IterableIterator |
| ------------ | :---: | :-----: | :-----: | :--------------: |
| `entries`    |   ✅   |    ✅    |    ✅    |        ❓         |
| `for ... in` |   ✅   |    🚧    |    ❓    |        ❓         |
| `for ... of` |   ✅   |    ✅    |    ✅    |        ❓         |
| `forEach`    |   ✅   |    ✅    |    ✅    |        ❓         |
| `keys`       |   ✅   |    🚧    |    ✅    |        ❓         |
| `values`     |   ✅   |    ✅    |    ✅    |        ❓         |

## Notes

### WeakSet and WeakMap

`WeakSet` and `WeakMap` are not iterable, and thus aren't included in this list. See [#1](https://github.com/MaximeKjaer/js-collections/issues/1) for more information.