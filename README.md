# Advanced Python — Comprehensive Jupyter Notebook Guide

Bu depo; Nesne Yönelimli Programlama (OOP), Python iç mekanikleri (internals), yerleşik fonksiyonlar, dosya yönetimi, eşzamanlılık (`asyncio`, `threading`, `multiprocessing`), birim testleri (`unittest` / `pytest`), en iyi uygulama pratikleri ve **Python 3.11 – 3.15** arası modern dil yeniliklerini uygulamalı kod örnekleriyle kapsayan kapsamlı bir çalışma rehberidir.

Tüm defterler (`advanced_python/*.ipynb`), temiz kod standartları, tip ek açıklamaları (type annotations) ve doğrudan çalıştırılabilir hücreler halinde yapılandırılmıştır.

> [!IMPORTANT]
> * **Python Sürümü:** Bu rehberdeki temel kod hücreleri **Python 3.10+** ile uyumludur; ancak sürüm yeniliklerini içeren defterler (`python311.ipynb` – `python315.ipynb`) dahil tüm hücreleri eksiksiz çalıştırmak için **Python 3.15** veya üzeri önerilir.
> * **Top-Level `await` (`asyncio.ipynb`):** Jupyter Notebook arka planda aktif bir *event loop* çalıştırdığı için `await` anahtar kelimesi global kapsamda doğrudan kullanılmıştır. Kodları standart bir `.py` dosyasında çalıştırırken `asyncio.run()` kullanmanız gerekir.
> * **`multiprocessing` Kısıtı (`multiprocessing.ipynb`):** `multiprocessing` modülü (özellikle Windows ve macOS'ta `spawn` başlangıç yöntemi nedeniyle) etkileşimli Jupyter hücrelerinde tanımlanan fonksiyonları alt süreçlere aktaramadığı için çalışmayabilir; bu örnekleri bağımsız bir `.py` dosyasında ve `if __name__ == '__main__':` bloğu içinde çalıştırmanız gerekir.

---

## İçindekiler (Repository Index)

### 1. [oop.ipynb](advanced_python/oop.ipynb)

Nesne Yönelimli Programlama temelleri, veri sınıfları, kalıtım, soyutlama, kapsülleme ve dunder metotları kapsar.

* [1. Classes & Objects (`__init__`)](advanced_python/oop.ipynb#1-classes--objects-__init__)
* [2. Class Attributes vs. Instance Attributes](advanced_python/oop.ipynb#2-class-attributes-vs-instance-attributes)
* [3. Methods (`@classmethod` & `@staticmethod`)](advanced_python/oop.ipynb#3-methods-classmethod--staticmethod)
* [4. Inheritance & `super()`](advanced_python/oop.ipynb#4-inheritance--super)
* [5. Abstract Base Classes (`abc` & `@abstractmethod`)](advanced_python/oop.ipynb#5-abstract-base-classes-abc--abstractmethod)
* [6. Encapsulation & Properties (`@property`)](advanced_python/oop.ipynb#6-encapsulation--properties-property)
* [7. Dunder (Magic) Methods & Operator Overloading](advanced_python/oop.ipynb#7-dunder-magic-methods--operator-overloading)
* [8. Dataclasses (`@dataclass`)](advanced_python/oop.ipynb#8-dataclasses-dataclass)

---

### 2. [pythonadvanced.ipynb](advanced_python/pythonadvanced.ipynb)

Python çalışma zamanı mekanikleri, bellek yönetimi, üreteçler, dekoratörler, bağlam yöneticileri ve fonksiyonel araçları inceler.

* [1. Generators & `yield`](advanced_python/pythonadvanced.ipynb#1-generators--yield)
* [2. Custom Iterators (`__iter__` & `__next__`)](advanced_python/pythonadvanced.ipynb#2-custom-iterators-__iter__--__next__)
* [3. Decorators & `functools.wraps`](advanced_python/pythonadvanced.ipynb#3-decorators--functoolswraps)
* [4. Context Managers (`with`, `__enter__`, `__exit__` & `contextlib`)](advanced_python/pythonadvanced.ipynb#4-context-managers-with-__enter__-__exit__--contextlib)
* [5. Structural Pattern Matching (`match` / `case`)](advanced_python/pythonadvanced.ipynb#5-structural-pattern-matching-match--case)
* [6. Closures & `nonlocal` Scope](advanced_python/pythonadvanced.ipynb#6-closures--nonlocal-scope)
* [7. Memory Management, References & `copy` vs. `deepcopy`](advanced_python/pythonadvanced.ipynb#7-memory-management-references--copy-vs-deepcopy)
* [8. Caching & Memoization (`@lru_cache` & `@cache`)](advanced_python/pythonadvanced.ipynb#8-caching--memoization-lru_cache--cache)

---

### 3. [builtins.ipynb](advanced_python/builtins.ipynb)

Python'ın yerleşik (built-in) fonksiyonlarını, veri dönüşümlerini, dinamik nesne sorgulamalarını ve ileri seviye koleksiyon yardımcılarını ele alır.

* [1. Functional Built-ins (`map`, `filter`, `zip`, `enumerate`)](advanced_python/builtins.ipynb#1-functional-built-ins-map-filter-zip-enumerate)
* [2. Aggregation & Logical Checks (`all`, `any`, `sum`, `min`, `max`, `sorted`)](advanced_python/builtins.ipynb#2-aggregation--logical-checks-all-any-sum-min-max-sorted)
* [3. Dynamic Introspection (`getattr`, `setattr`, `hasattr`, `isinstance`, `issubclass`)](advanced_python/builtins.ipynb#3-dynamic-introspection-getattr-setattr-hasattr-isinstance-issubclass)
* [4. Code Evaluation & Representation (`eval`, `exec`, `repr`, `ascii`, `chr`, `ord`)](advanced_python/builtins.ipynb#4-code-evaluation--representation-eval-exec-repr-ascii-chr-ord)
* [5. Memory & Numeric Built-ins (`memoryview`, `bytearray`, `divmod`, `pow`, `round`)](advanced_python/builtins.ipynb#5-memory--numeric-built-ins-memoryview-bytearray-divmod-pow-round)

---

### 4. [filemanagement.ipynb](advanced_python/filemanagement.ipynb)

Dosya okuma/yazma işlemleri, modern `pathlib` kullanımı, JSON/CSV serileştirme ve arşiv yönetimini açıklar.

* [1. Modern Path Operations with `pathlib.Path`](advanced_python/filemanagement.ipynb#1-modern-path-operations-with-pathlibpath)
* [2. Reading & Writing Text/Binary Files Safely](advanced_python/filemanagement.ipynb#2-reading--writing-textbinary-files-safely)
* [3. Working with JSON & CSV Data](advanced_python/filemanagement.ipynb#3-working-with-json--csv-data)
* [4. Object Serialization (`pickle`) & Temporary Files (`tempfile`)](advanced_python/filemanagement.ipynb#4-object-serialization-pickle--temporary-files-tempfile)
* [5. High-Level File Operations (`shutil` & `glob`)](advanced_python/filemanagement.ipynb#5-high-level-file-operations-shutil--glob)

---

### 5. [multithreading.ipynb](advanced_python/multithreading.ipynb)

G/Ç (I/O) yoğunluklu görevler için iş parçacığı yönetimi, eşzamanlama kilitleri ve havuz yürütücülerini inceler.

* [1. Creating & Managing Threads (`threading.Thread`)](advanced_python/multithreading.ipynb#1-creating--managing-threads-threadingthread)
* [2. Race Conditions & Synchronization (`Lock` & `RLock`)](advanced_python/multithreading.ipynb#2-race-conditions--synchronization-lock--rlock)
* [3. Thread Signaling & Coordination (`Event`, `Semaphore`, `Queue`)](advanced_python/multithreading.ipynb#3-thread-signaling--coordination-event-semaphore-queue)
* [4. High-Level Concurrency with `ThreadPoolExecutor`](advanced_python/multithreading.ipynb#4-high-level-concurrency-with-threadpoolexecutor)

---

### 6. [multiprocessing.ipynb](advanced_python/multiprocessing.ipynb)

CPU yoğunluklu işlemlerde çok çekirdekli gerçek paralellik, süreçler arası iletişim ve paylaşımlı bellek yapılarını kapsar.

* [1. Spawning Processes (`multiprocessing.Process`)](advanced_python/multiprocessing.ipynb#1-spawning-processes-multiprocessingprocess)
* [2. Inter-Process Communication (`Queue` & `Pipe`)](advanced_python/multiprocessing.ipynb#2-inter-process-communication-queue--pipe)
* [3. Shared State (`Value`, `Array` & `Manager`)](advanced_python/multiprocessing.ipynb#3-shared-state-value-array--manager)
* [4. Process Pools (`Pool` & `ProcessPoolExecutor`)](advanced_python/multiprocessing.ipynb#4-process-pools-pool--processpoolexecutor)

---

### 7. [asyncio.ipynb](advanced_python/asyncio.ipynb)

Tek iş parçacıklı olay döngüsü (event loop) üzerinde asenkron programlama, coroutine'ler ve eşzamanlı görev koordinasyonunu öğretir.

* [1. Coroutines, `async` / `await` & Event Loop Basics](advanced_python/asyncio.ipynb#1-coroutines-async--await--event-loop-basics)
* [2. Creating & Scheduling Tasks (`asyncio.create_task`)](advanced_python/asyncio.ipynb#2-creating--scheduling-tasks-asynciocreate_task)
* [3. Running Concurrent Coroutines (`asyncio.gather` & `as_completed`)](advanced_python/asyncio.ipynb#3-running-concurrent-coroutines-asynciogather--as_completed)
* [4. Timeouts, Cancellation & Async Context Managers (`async with` / `async for`)](advanced_python/asyncio.ipynb#4-timeouts-cancellation--async-context-managers-async-with--async-for)

---

### 8. [unittesting.ipynb](advanced_python/unittesting.ipynb)

Yazılım doğrulama, birim testleri, fixture kurulumları, parametrik testler ve mock nesnelerini ele alır.

* [1. Core Assertions & Test Cases (`unittest.TestCase`)](advanced_python/unittesting.ipynb#1-core-assertions--test-cases-unittesttestcase)
* [2. Test Lifecycle (`setUp` & `tearDown`)](advanced_python/unittesting.ipynb#2-test-lifecycle-setup--teardown)
* [3. Testing Exceptions & Edge Cases (`assertRaises`)](advanced_python/unittesting.ipynb#3-testing-exceptions--edge-cases-assertraises)
* [4. Mocking & Patching Dependencies (`unittest.mock`)](advanced_python/unittesting.ipynb#4-mocking--patching-dependencies-unittestmock)

---

### 9. [tipstricks.ipynb](advanced_python/tipstricks.ipynb)

Performans ipuçları, statik kod analizi, biçimlendirme incelikleri ve dil içi konvansiyonları içerir.

* [1. Advanced F-String Formatting (Alignment, Fill, Precision & Scientific Notation)](advanced_python/tipstricks.ipynb#1-advanced-f-string-formatting-alignment-fill-precision--scientific-notation)
* [2. Tuples & Type Hinting (`tuple[T, ...]`)](advanced_python/tipstricks.ipynb#2-tuples--type-hinting-tuplet-)
* [3. Flattening Nested Lists (List Comprehension & Recursion)](advanced_python/tipstricks.ipynb#3-flattening-nested-lists-list-comprehension--recursion)
* [4. The Ellipsis Object (`...`)](advanced_python/tipstricks.ipynb#4-the-ellipsis-object-)
* [5. Static Code Analysis & Linting (`pylint`)](advanced_python/tipstricks.ipynb#5-static-code-analysis--linting-pylint)
* [6. Suppressing Linter Rules (`# noqa`)](advanced_python/tipstricks.ipynb#6-suppressing-linter-rules--noqa)
* [7. Efficient String Concatenation (`+` vs. `''.join()`)](advanced_python/tipstricks.ipynb#7-efficient-string-concatenation--vs-join)
* [8. Backslashes (`\`): Escape Sequences & Line Continuation](advanced_python/tipstricks.ipynb#8-backslashes--escape-sequences--line-continuation)
* [9. Common Uses of the Underscore (`_`)](advanced_python/tipstricks.ipynb#9-common-uses-of-the-underscore-_)
* [10. Python `list` vs. `array.array`](advanced_python/tipstricks.ipynb#10-python-list-vs-arrayarray)

---

### 10. [python311.ipynb](advanced_python/python311.ipynb)

Python 3.11 ile gelen yapısal eşzamanlılık, hata gruplama ve `Self` tip açıklaması özelliklerini kapsar.

* [1. `ExceptionGroup` & `except*` Syntax](advanced_python/python311.ipynb#1-exceptiongroup--except-syntax)
* [2. Structured Concurrency with `asyncio.TaskGroup`](advanced_python/python311.ipynb#2-structured-concurrency-with-asynciotaskgroup)
* [3. The `typing.Self` Type Annotation](advanced_python/python311.ipynb#3-the-typingself-type-annotation)

---

### 11. [python312.ipynb](advanced_python/python312.ipynb)

Python 3.12 ile eklenen yeni tip parametresi sözdizimi, esnek f-string kuralları ve düşük maliyetli izleme araçlarını kapsar.

* [1. Type Parameter Syntax & `type` Statement (PEP 695)](advanced_python/python312.ipynb#1-type-parameter-syntax--type-statement-pep-695)
* [2. Syntactic Formalization of F-Strings (PEP 701)](advanced_python/python312.ipynb#2-syntactic-formalization-of-f-strings-pep-701)
* [3. `@typing.override` Decorator (PEP 698)](advanced_python/python312.ipynb#3-typingoverride-decorator-pep-698)
* [4. Python Buffer Protocol (`collections.abc.Buffer` & `__buffer__`) (PEP 688)](advanced_python/python312.ipynb#4-python-buffer-protocol-collectionsabcbuffer--__buffer__-pep-688)
* [5. Comprehension Inlining (PEP 709) & Low-Impact Monitoring (`sys.monitoring`) (PEP 669)](advanced_python/python312.ipynb#5-comprehension-inlining-pep-709--low-impact-monitoring-sysmonitoring-pep-669)

---

### 12. [python313.ipynb](advanced_python/python313.ipynb)

Python 3.13 ile sunulan No-GIL (free-threaded) mimarisi, deneysel JIT ve yeni tip sistemi araçlarını inceler.

* [1. Free-Threaded CPython (No-GIL) & Experimental JIT Compiler (PEP 703 & PEP 744)](advanced_python/python313.ipynb#1-free-threaded-cpython-no-gil--experimental-jit-compiler-pep-703--pep-744)
* [2. Type Parameter Defaults (`[T = DefaultType]`) (PEP 696)](advanced_python/python313.ipynb#2-type-parameter-defaults-t--defaulttype-pep-696)
* [3. `@warnings.deprecated` Decorator (PEP 702)](advanced_python/python313.ipynb#3-warningsdeprecated-decorator-pep-702)
* [4. `typing.ReadOnly` for `TypedDict` (PEP 705) & `typing.TypeIs` (PEP 742)](advanced_python/python313.ipynb#4-typingreadonly-for-typeddict-pep-705--typingtypeis-pep-742)
* [5. Defined `locals()` Semantics (PEP 667), Interactive REPL & Standard Library Updates](advanced_python/python313.ipynb#5-defined-locals-semantics-pep-667-interactive-repl--standard-library-updates)

---

### 13. [python314.ipynb](advanced_python/python314.ipynb)

Python 3.14 ile gelen `t-strings`, ertelenmiş tip açıklamaları, alt yorumlayıcı havuzu ve Zstandard sıkıştırmasını kapsar.

* [1. Template String Literals (`t-strings`) (PEP 750)](advanced_python/python314.ipynb#1-template-string-literals-t-strings-pep-750)
* [2. Deferred Evaluation of Annotations (PEP 649 & PEP 749)](advanced_python/python314.ipynb#2-deferred-evaluation-of-annotations-pep-649--pep-749)
* [3. Multiple Interpreters in the Standard Library (`concurrent.interpreters`) (PEP 734)](advanced_python/python314.ipynb#3-multiple-interpreters-in-the-standard-library-concurrentinterpreters-pep-734)
* [4. Bracketless Exception Tuple Syntax (PEP 758) & `finally` Control-Flow Restriction (PEP 765)](advanced_python/python314.ipynb#4-bracketless-exception-tuple-syntax-pep-758--finally-control-flow-restriction-pep-765)
* [5. Zstandard Compression (`compression.zstd`) (PEP 784), Zero-Overhead External Debugger (PEP 768) & Tail-Call Interpreter](advanced_python/python314.ipynb#5-zstandard-compression-compressionzstd-pep-784-zero-overhead-external-debugger-pep-768--tail-call-interpreter)

---

### 14. [python315.ipynb](advanced_python/python315.ipynb)

Python 3.15 ile eklenen yüksek frekanslı istatistiksel profilleyici, varsayılan UTF-8 modu ve `lazy import` sözdizimini inceler.

* [1. High-Frequency Statistical Sampling Profiler (`profiling.sampling` / `Tachyon`) (PEP 799)](advanced_python/python315.ipynb#1-high-frequency-statistical-sampling-profiler-profilingsampling--tachyon-pep-799)
* [2. UTF-8 Mode Enabled by Default Across All Platforms (PEP 686)](advanced_python/python315.ipynb#2-utf-8-mode-enabled-by-default-across-all-platforms-pep-686)
* [3. Lazy Imports (`lazy import` & `lazy from ... import`) (PEP 810)](advanced_python/python315.ipynb#3-lazy-imports-lazy-import--lazy-from--import-pep-810)
* [4. `PyBytesWriter` C-API (PEP 782), Explicit `int`/Index Conversions & `math.integer` Updates](advanced_python/python315.ipynb#4-pybyteswriter-c-api-pep-782-explicit-intindex-conversions--mathinteger-updates)
* [5. Dedicated `math.integer` Module & Improved Error Diagnostics](advanced_python/python315.ipynb#5-dedicated-mathinteger-module--improved-error-diagnostics)
