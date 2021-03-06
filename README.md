Kotter Knife
============

![](art/logo.png)

[Butter Knife][1]-esque view binding for Kotlin.

```kotlin
public class PersonView(context: Context, attrs: AttributeSet?) : LinearLayout(context, attrs) {
  val firstName: TextView by bindView(R.id.first_name)
  val lastName: TextView by bindView(R.id.last_name)

  // Optional binding.
  val details: TextView? by bindOptionalView(R.id.details)

  // List binding.
  val nameViews: List<TextView> by bindViews(R.id.first_name, R.id.last_name)

  // List binding with optional items being omitted.
  val nameViews: List<TextView> by bindOptionalViews(R.id.first_name, R.id.middle_name, R.id.last_name)

  // Binding elements to custom container
  class ExampleViewContainer(view: View) : ViewContainer(view) {
    val name: View by bindView(R.id.name)
  }
  var container: ExampleViewContainer by Delegates.notNull()
  container = ExampleViewContainer(someView)
}
```

These methods are available on subclasses of `Activity`, `Dialog`, `ViewGroup`, `Fragment`,
the support library `Fragment`, and recycler view's `ViewHolder` or custom container based on `ViewContainer`.



Download
--------

Currently not available via Maven Central.

A SNAPSHOT is available in the Sonatype snapshot repo.
```groovy
compile 'com.jakewharton:kotterknife:0.1.0-SNAPSHOT'
```

You can also copy `ButterKnife.kt` into your source tree. The file depends on the 'support-v4' and
'recyclerview-v7' libraries but the dependency is easily removed by deleting a few lines.

Comments, suggestions, and pull requests are encouraged!



License
-------

    Copyright 2014 Jake Wharton

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.


 [1]: http://jakewharton.github.io/butterknife
