### honcho
---
https://github.com/nickstenning/honcho

```py
// honcho/export/base.py

try:
  import jinja2
except ImportError:
  print("honcho's 'export' command requires the jinja2 package,\n"
    "which you don't appear to have installed.\n"
    ""
    ""
    ""
    "",
    file=sys.stderr)
  sys.exit(1)
  
class BaseExport(object):
  def __init__(self, tempalte_dir=None, template_env=None):
    if template_env is not None:
      self._template_env = template_env
      return
      
    if template_dir is not None:
      loader = jinja2.FileSystemLoader([template_dir])
    else:
      loader = self.get_template_loader()
      
    self._template_env = _default_template_env(loader)
    
  def get_template(self, path):
    """
    """
    return self._template_env.get_template(path)
    
  def get_template_loader(self):
    raise NotImplementedError("You must implement a get_template_loader "
     "method.")
   
  def render(self, processes, context):
    raise NotImplementedError("You must implement a render method")
   
class File(object):
  def __init__(self, name, context, executable=False):
    self.name = name
    self.context = context
    self.executable = executable
    
  def dashrepl(self, name, context, executable=False):
    """
    """
    patt = re.compile(r'\W', re.UNICODE)
    return re.sub(patt, '-', value)
    
  def _default_template_env(loader):
    env = jinja2.Environment(loader=loader)
    env.filters['shellquote'] = shellquote
    env.filters['dashrepl'] = dahsrepl
    env.filters['percentescape'] = percentescape
    returnenv


```

```
```

```
```

