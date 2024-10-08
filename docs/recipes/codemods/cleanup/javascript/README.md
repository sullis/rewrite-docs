# Javascript

## Recipes

* [Disallow awaiting non-promise values.](./nounnecessaryawait.md)
* [Disallow classes that only have static members.](./nostaticonlyclass.md)
* [Disallow comparing `undefined` using `typeof`.](./notypeofundefined.md)
* [Disallow else blocks after return statements in if statements](./noelsereturn.md)
* [Disallow equal signs explicitly at the beginning of regular expressions](./nodivregex.md)
* [Disallow `if` statements as the only statement in `if` blocks without `else`.](./nolonelyif.md)
* [Disallow initializing variables to undefined](./noundefinit.md)
* [Disallow member access from `await` expression.](./noawaitexpressionmember.md)
* [Disallow negated conditions.](./nonegatedcondition.md)
* [Disallow nested ternary expressions.](./nonestedternary.md)
* [Disallow `new Array()`.](./nonewarray.md)
* [Disallow number literals with zero fractions or dangling dots.](./nozerofractions.md)
* [Disallow `parseInt()` and `Number.parseInt()` in favor of binary, octal, and hexadecimal literals](./prefernumericliterals.md)
* [Disallow redundant return statements](./nouselessreturn.md)
* [Disallow renaming import, export, and destructured assignments to the same name](./nouselessrename.md)
* [Disallow returning/yielding `Promise.resolve()`/`reject()` in `async` functions or promise callbacks.](./nouselesspromiseresolvereject.md)
* [Disallow shorthand type conversions](./noimplicitcoercion.md)
* [Disallow ternary operators when simpler alternatives exist](./nounneededternary.md)
* [Disallow the use of `Math.pow` in favor of the ** operator](./preferexponentiationoperator.md)
* [Disallow the use of the `null` literal.](./nonull.md)
* [Disallow unnecessary calls to `.bind()`](./noextrabind.md)
* [Disallow unnecessary computed property keys in objects and classes](./nouselesscomputedkey.md)
* [Disallow unnecessary labels](./noextralabel.md)
* [Disallow unnecessary spread.](./nouselessspread.md)
* [Disallow unreadable array destructuring.](./nounreadablearraydestructuring.md)
* [Disallow use of `Object.prototype.hasOwnProperty.call()` and prefer use of `Object.hasOwn(`)](./preferobjecthasown.md)
* [Disallow useless array `length` check.](./nouselesslengthcheck.md)
* [Disallow useless fallback when spreading in object literals.](./nouselessfallbackinspread.md)
* [Disallow useless `undefined`.](./nouselessundefined.md)
* [Disallow using `Object.assign` with an object literal as the first argument and prefer the use of object spread instead](./preferobjectspread.md)
* [Disallow using the `this` argument in array methods.](./noarraymethodthisargument.md)
* [Do not use a `for` loop that can be replaced with a `for-of` loop.](./noforloop.md)
* [Do not use leading/trailing space between `console.log` parameters.](./noconsolespaces.md)
* [Enforce a convention in module import order](./order.md)
* [Enforce a newline after import statements](./newlineafterimport.md)
* [Enforce a particular style for multiline comments](./multilinecommentstyle.md)
* [Enforce a specific parameter name in catch clauses.](./catcherrorname.md)
* [Enforce better string content.](./stringcontent.md)
* [Enforce combining multiple `Array#push()` into one call.](./noarraypushpush.md)
* [Enforce consistent brace style for all control statements](./curly.md)
* [Enforce consistent brace style for case clauses.](./switchcasebraces.md)
* [Enforce consistent case for text encoding identifiers.](./textencodingidentifiercase.md)
* [Enforce consistent relative URL style.](./relativeurlstyle.md)
* [Enforce correct `Error` subclassing.](./customerrordefinition.md)
* [Enforce dot notation whenever possible](./dotnotation.md)
* [Enforce explicitly comparing the length or size property of a value.](./explicitlengthcheck.md)
* [Enforce no spaces between braces.](./emptybracespaces.md)
* [Enforce or ban the use of inline type-only markers for named imports](./consistenttypespecifierstyle.md)
* [Enforce or disallow capitalization of the first letter of a comment](./capitalizedcomments.md)
* [Enforce proper case for numeric literals.](./numberliteralcase.md)
* [Enforce sorted import declarations within modules](./sortimports.md)
* [Enforce the style of numeric separators by correctly grouping digits.](./numericseparatorsstyle.md)
* [Enforce the use of `Buffer.from()` and `Buffer.alloc()` instead of the deprecated `new Buffer()`.](./nonewbuffer.md)
* [Enforce the use of `Math.trunc()` instead of bitwise operators.](./prefermathtrunc.md)
* [Enforce the use of Unicode escapes instead of hexadecimal escapes.](./nohexescape.md)
* [Enforce the use of `new` for all builtins, except `String`, `Number`, `Boolean`, `Symbol`, and `BigInt`.](./newforbuiltins.md)
* [Enforce throwing `TypeError` in type checking conditions.](./prefertypeerror.md)
* [Enforce using the digits argument with `Number#toFixed()`.](./requirenumbertofixeddigitsargument.md)
* [Enforce using the separator argument with `Array#join()`.](./requirearrayjoinseparator.md)
* [Enforce variables to be declared either together or separately in functions](./onevar.md)
* [Ensure all imports appear before other statements](./first.md)
* [Fix whitespace-insensitive template indentation.](./templateindent.md)
* [Forbid empty named import](./noemptynamedblocks.md)
* [Forbid import of modules using absolute paths](./noabsolutepath.md)
* [Forbid import statements with CommonJS module.exports](./noimportmoduleexports.md)
* [Forbid importing packages through relative paths](./norelativepackages.md)
* [Forbid namespace (a.k.a. "wildcard" `*`) imports.](./nonamespace.md)
* [Forbid repeated import of the same module in multiple places](./noduplicates.md)
* [Forbid unnecessary path segments in import and require statements](./nouselesspathsegments.md)
* [Improve regexes by making them shorter, consistent, and safer.](./betterregex.md)
* [Prefer `.addEventListener()` and `.removeEventListener()` over on-functions.](./preferaddeventlistener.md)
* [Prefer `.at()` method for index access and `String#charAt()`.](./preferat.md)
* [Prefer `.before()` over `.insertBefore()`, `.replaceWith()` over `.replaceChild()`, prefer one of `.before()`, `.after()`, `.append()` or `.prepend()` over `insertAdjacentText()` and `insertAdjacentElement()`.](./prefermoderndomapis.md)
* [Prefer `.find()` and `.findLast()` over the first or last element from `.filter()`.](./preferarrayfind.md)
* [Prefer `.flatMap()` over `.map().flat()`.](./preferarrayflatmap.md)
* [Prefer `.includes()` over `.indexOf()` and `Array#some()` when checking for existence or non-existence.](./preferincludes.md)
* [Prefer `.querySelector()` over `.getElementById()`, `.querySelectorAll()` over `.getElementsByClassName()` and `.getElementsByTagName()`.](./preferqueryselector.md)
* [Prefer `.some()` over `.filter().length` check and `.{find,findLast}()`.](./preferarraysome.md)
* [Prefer `Array#flat()` over legacy techniques to flatten arrays.](./preferarrayflat.md)
* [Prefer `Array#{indexOf,lastIndexOf}()` over `Array#{findIndex,findLastIndex}()` when looking for the index of an item.](./preferarrayindexof.md)
* [Prefer `Date.now()` to get the number of milliseconds since the Unix Epoch.](./preferdatenow.md)
* [Prefer JavaScript modules (ESM) over CommonJS.](./prefermodule.md)
* [Prefer `KeyboardEvent#key` over `KeyboardEvent#keyCode`.](./preferkeyboardeventkey.md)
* [Prefer `Node#append()` over `Node#appendChild()`.](./preferdomnodeappend.md)
* [Prefer `Number` static properties over global ones.](./prefernumberproperties.md)
* [Prefer `Reflect.apply()` over `Function#apply()`.](./preferreflectapply.md)
* [Prefer `RegExp#test()` over `String#match()` and `RegExp#exec()`.](./preferregexptest.md)
* [Prefer `Set#has()` over `Array#includes()` when checking for existence or non-existence.](./prefersethas.md)
* [Prefer `String#replaceAll()` over regex searches with the global flag.](./preferstringreplaceall.md)
* [Prefer `String#slice()` over `String#substr()` and `String#substring()`.](./preferstringslice.md)
* [Prefer `String#startsWith()` & `String#endsWith()` over `RegExp#test()`.](./preferstringstartsendswith.md)
* [Prefer `String#trimStart()` / `String#trimEnd()` over `String#trimLeft()` / `String#trimRight()`.](./preferstringtrimstartend.md)
* [Prefer borrowing methods from the prototype instead of the instance.](./preferprototypemethods.md)
* [Prefer `childNode.remove()` over `parentNode.removeChild(childNode)`.](./preferdomnoderemove.md)
* [Prefer default parameters over reassignment.](./preferdefaultparameters.md)
* [Prefer `export…from` when re-exporting.](./preferexportfrom.md)
* [Prefer `for…of` over the `forEach` method.](./noarrayforeach.md)
* [Prefer modern Math APIs over legacy patterns.](./prefermodernmathapis.md)
* [Prefer negative index over `.length - index` when possible.](./prefernegativeindex.md)
* [Prefer omitting the catch binding parameter.](./preferoptionalcatchbinding.md)
* [Prefer reading a JSON file as a buffer.](./preferjsonparsebuffer.md)
* [Prefer `switch` over multiple `else-if`.](./preferswitch.md)
* [Prefer ternary expressions over simple `if-else` statements.](./preferternary.md)
* [Prefer the spread operator over `Array.from()`, `Array#concat()`, `Array#{slice,toSpliced}()` and `String#split('')`.](./preferspread.md)
* [Prefer using `.dataset` on DOM elements over calling attribute methods.](./preferdomnodedataset.md)
* [Prefer using `Object.fromEntries()` to transform a list of key-value pairs into an object.](./preferobjectfromentries.md)
* [Prefer using `Set#size` instead of `Array#length`.](./prefersetsize.md)
* [Prefer using `String`, `Number`, `BigInt`, `Boolean`, and `Symbol` directly.](./prefernativecoercionfunctions.md)
* [Prefer using the `node:` protocol when importing Node.js builtin modules.](./prefernodeprotocol.md)
* [Prevent abbreviations.](./preventabbreviations.md)
* [Require `Array.isArray()` instead of `instanceof Array`.](./noinstanceofarray.md)
* [Require braces around arrow function bodies](./arrowbodystyle.md)
* [Require const declarations for variables that are never reassigned after declared](./preferconst.md)
* [Require destructuring from arrays and/or objects](./preferdestructuring.md)
* [Require escape sequences to use uppercase values.](./escapecase.md)
* [Require `let` or `const` instead of `var`](./novar.md)
* [Require `new` when throwing an error.](./thrownewerror.md)
* [Require or disallow "Yoda" conditions](./yoda.md)
* [Require or disallow Unicode byte order mark (BOM)](./unicodebom.md)
* [Require or disallow assignment operator shorthand where possible](./operatorassignment.md)
* [Require or disallow logical assignment operator shorthand](./logicalassignmentoperators.md)
* [Require or disallow method and property shorthand syntax for object literals](./objectshorthand.md)
* [Require or disallow strict mode directives](./strict.md)
* [Require template literals instead of string concatenation](./prefertemplate.md)
* [Require the use of `===` and `!==`](./eqeqeq.md)
* [Require using arrow functions for callbacks](./preferarrowcallback.md)
* [Require variables within the same declaration block to be sorted](./sortvars.md)
* [Use destructured variables over properties.](./consistentdestructuring.md)

