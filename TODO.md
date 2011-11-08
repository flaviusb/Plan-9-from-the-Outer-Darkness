Notes
-----

- Really Quite Sane OS (RQS*X). Plan 9 from the Outer Darkness.
- Sanity.
- Voice, Exit, Legitimacy
- Stabbing. Papercuts. Numbness. Neglect (in the sense of hemispherical neglect). Scars.
- Interrogatability.
- Consistency.
- Discoverability.
- Difference between surface model and actual model. Hysterisis vs being led to the correct conclusion.
- Sharp edges?
- Discontinuities, and leaky abstractions.

Building blocks
---------------

- Language
  - Minilang that can be compiled to the start of the microkernel
  - Runtime libraries
- REST
- Queues
- Sockets as they should be
- Files
- Mounts
- Paths/URIs
- OAuth alike
- Basic datatypes/mimetypes that should be known: netstrings, tnetstrings, JSON, XML, Yaml, ASN.1?
- Servers
  - Base FS
  - Authorization/Keystore/Etc
  - Heartbeat
  - Ressurection
  - GC?
  - Devices?


Stuff I want to remember to use for stuff
Rubinius: As basis for a VM for Ioke?
Ometa/Cola/Idst - Implement the core of this into my version of Ioke, or into a core language, or to use for code gen



Stuff
-----

- VM
- GC
- Object model/FFI (These are so intimately related)
- MOP - a la AMOP, Moose, Ioke/Self etc
- Pattern Matching
- Extractor objects, a la Scala case classes
- PEG - eg Ometa, Peggy, Cola, Idst
- Quasiquotation, unquotation, quotation, code manipulation and generation - Like in Lisp or Ioke, or possibly MetaLua or Template Haskell
- Macros: regular, read, fexprs, lecros, syntaxes, destructuring
  - regular or read
  - lexical, method, partial, or flat
  - inline splat, or whole?
  - evaluating arguments or not (ie, macro, something, or fexpr)
  - destructuring or not
  - pandoric or not
  - once only inline replacement, or actual evaluation
  - Hygenic or not (default: not)
  - Other only partially orthogonal possibilities: Syntax Rules, ...
- Type system (Haskell, ML, Agda, Scala...) + inference. Pluggable, optional etc. Actual type algebra that stuff can operate on.
- Module system (Modules in ML as functors, CommonJS CommonJS things, Ruby Gems, Erlang export thing library hashes)
  - Not sure how I want namespaces to work with this.
- Sugaring/desugaring
- Berjillions of literal types (ie 'qw(foo bar baz)', '/a+b?(cd*)+/xg') implemented through sugaring/desugaring via Peg, Quasiquotation, the MOP, and read macros. Perl and Ruby both do really good/evil stuff here.
  - 'Infix', 'Prefix', 'Suffix', 'Ternary', and 'Around' operators, with quoting, splitting, precedence, reordering, shuffling, slurping rules.
- Custom reader stuff
- Pretty printers of various sorts

Metaprogramming through
- MOP
- Quasiquotation
- PEG
- Type system - (Type level computation, implicits, etc)
- Tower - Parsers - Metacircular evaluator
- Sugaring/Desugaring (esp like how Haskell does it)

Data languages
- Query language
- XML+stuff lang (test: can one implement both CellML and RDF cleanly on top of it)
- JSON
- Different representations of code
  - Ie various whitespace sensitive skins
  - Repetition and combination syntax
  - Concatenative/stack stuff?
  - Chaining syntax
  - Layered dictionary syntax a la ☝
- Like _why's code/data langs in Potion
- But also unquotation and fragments, so that stuff can be 'mushed together'/'inside out interpolated'.
- Verified correctness by types
- Compiled fragment with holes that can be interpolated; function that takes stuff to put in the holes and returns a filled in blob.


Scope/Projects
--------------

- New CellML API
- Linear Algebra system
- Units
- Widget Toolkit/Gui Toolkit
- Pango/Cairo wrapper/replacement
- Ideally, full stack Widget/Gui/Pango/Cairo/X. But unlikely.
- HTML generation - both Byeloblog and Yesod should be inspirations
- Form generator generator
- Code generation for other languages for some use eg ☟
- FFI code wrapper generator from interface description language
- HTTP stack + reverse proxy
  - Stuff on top of basic http stack: content negotiation, mime types, how to deal with response codes, stuff to make HATEOAS more natural, header parsing and response...
- Database lib
  - Queries always safe by construction etc
- Restful file system/system apis?
- 'Pipe' as HTTP

Widget toolkit
--------------

- Bind stuff in with data languages
- Compiled forms a la xml builders for *structure*
- CSS equivalent for *style*
- Data language for *content*
- Sane databinding, esp from containers to container type widgets
- Push, pull, queue, query, synthetic, replace, insert
- To repeat, I goddamn want something like the HTML/CSS split so that I can reskin, rip apart, remix etc apps reasonably sanely.
- Widgets that must exist:
  - A decent treeview
  - Buttons
  - Divs, spans, paras, uls, ols, lis, textareas, labels, forms of some description
  - Cards
  - Tabbed panels
  - Stacks
  - Flows
  - Checkboxes
- Widgets must have shadow dom, pseudo elements etc. There must also be a way of creating more of these
- CSS alike must have:
  - css grid
  - styling a la css level 1 and 2
  - shadow dom selectors
  - pseudo selectors
  - XBL like stuff

HATEOAS fs
----------

- No '.' and '..' files
- ls etc return/mainpulate a list of files in 'link' form
  - ie if mimetype: application/xml is negotiated: <files><link href="/foo/bar/" rel="parent"/><link href="/foo/bar/baz/" rel="self"/><link href="/foo/bar/baz/quux/" rel="contained directory"/><link href="/foo/bar/baz/dingbat" rel="contained file"/></files>
- Hateoas for system apis
- servers serve mountable points that ...
- HTTPize stuff; mime-types, response codes, content negotiation
- sockets - look up zeromq stuff for different socket types. Multicast, ipflood, pingback etc at the very least.
- Queues must also be supported somehow
- OAuth alike authorization, with various revocable permissions
- Manifests on executables specifying what permissions they want
- Servers can require various permissions to mount various directories

Replacement for Man
-------------------

- Who: Who wrote this? Person, group, organization? Who is it for? Who is the intended audience (ie user, admin, developer, designer, power user, auditor etc)? What is the expected background? What do I need to learn before I can use this (eg what is the expected level of knowledge, and where can I find this knowledge)?
- What: What is this. Short decription first, followed by options, and then long description of how to use it. This is the most similar to the usual contents of a man page.
- When: What are the use cases? When would I use this?
- Where: Where are all the various bits of this? The binary, the libraries, the configuration and logging files...
- Why: Why is this the way it is? What major decisions have shaped it? What are the caveats?
- Which: Like debian-alternatives. Which things have this name, and which one is currently invoked by this command.
- Whence: Where does this come from: repo, web page, package etc. Install/update/remove instructions.
- Look: Gives the complete list of info commands that are supported on a command (ie Who, What, but not Where or When...)
- Dependencies: The packages that a package depends on.

New gem/deb/apt/egg like format
-------------------------------

- Contains the info for Who, What, When, Where, Why, Which, Whence etc
- Contains dependencies
- Contains source repo location
- Contains build/install/remove recipe
- Contains exports info (a la CommonJS)
- Reverse package manager also a la Cupboard https://github.com/spiceapps/cupboard

Intents system
--------------

- Intents server?
