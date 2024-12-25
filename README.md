# Bootstrap Multiple Modal Overlay

## Bootstrap Modal
```
<button type="button" class="btn btn-primary" data-toggle="modal" data-target="#exampleModal">
  Launch demo modal
</button>

<!-- Modal -->
<div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="exampleModalLabel">Modal title</h5>
        <button type="button" class="close" data-dismiss="modal" aria-label="Close">
          <span aria-hidden="true">×</span>
        </button>
      </div>
      <div class="modal-body">
        ...
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary">Save changes</button>
      </div>
    </div>
  </div>
</div>
```

## Multiple Bootstrap Modals
```
<button type="button" class="btn btn-primary" data-toggle="modal" data-target="#exampleModal">
 Launch demo modal
</button>

<!-- Modal -->
<div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
 <div class="modal-dialog">
   <div class="modal-content">
     <div class="modal-header">
       <h5 class="modal-title" id="exampleModalLabel">Modal title</h5>
       <button type="button" class="close" data-dismiss="modal" aria-label="Close">
         <span aria-hidden="true">×</span>
       </button>
     </div>
     <div class="modal-body">
       ...
     </div>
     <div class="modal-footer">
       <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
       <button type="button" class="btn btn-primary" data-toggle="modal" data-target="#exampleModal2">Save changes</button> 
     </div>
   </div>
 </div>
</div>
<div class="modal fade" id="exampleModal2">
 <div class="modal-dialog">
   <div class="modal-content">
     <div class="modal-header">
       <h5 class="modal-title" id="exampleModalLabel">Are You Ok</h5>
       <button type="button" class="close" data-dismiss="modal" aria-label="Close">
         <span aria-hidden="true">×</span>
       </button>
     </div>
     <div class="modal-body">
       ...
     </div>
     <div class="modal-footer">
       <button type="button" class="btn btn-secondary" data-dismiss="modal">Cancel</button>
       <button type="button" class="btn btn-primary">OK</button>
     </div>
   </div>
 </div>
</div>
```

## CSS
```
.modal-second {
  z-index: 1052;
}

.modal-backdrop.fade {
  & + .modal-backdrop.fade {
    z-index: 1051;
  }
}
```

## JS
```
$(document).on('hidden.bs.modal', function () {
  if ($('.modal:visible').length) {
    $('body').addClass('modal-open');
  }
});
```

# Step modal
```
<button type="button" class="btn btn-primary" data-toggle="modal" data-target="#exampleModal">
  Launch demo modal
</button>

<!-- Modal -->
<div class="modal fade" id="exampleModal">
  <div class="modal-dialog">
    <div class="modal-content"
      <div class="modal-body">
         <div class="step js-steps-content" id="step1">
           <h4>Title step1</h4>
           <div class="d-flex">
               <button type="button" class="btn btn-secondary" data-dismiss="modal">Cancel</button>
              <button type="button" class="btn btn-primary js-step" data-show="step2">OK</button>
            </div>
         </div>
         <div class="step js-steps-content step-hide" id="step2">
           <h4>Title step2</h4>
           <div class="d-flex">
               <button type="button" class="btn btn-secondary js-step" data-show="step1">Cancel</button>
              <button type="button" class="btn btn-primary" data-dismiss="modal">OK</button>
            </div>
         </div>
      </div>
    </div>
  </div>
</div>
```

## CSS
```
.step-hide {
   display: none;
}
```

## JS
```
$(document).on(click, '.js-step', function(e) {
    e.stopPropagation();
    var attrStep = $(this).attr('data-show');
    $(this).parents('.js-steps-content').hide();
    $(attrStep).show();
});
```

# References
+ https://viblo.asia/p/huong-dan-lam-multiple-bootstrap-modals-va-step-modal-bootstrap-don-gian-chi-trong-15-phut-924lJ4MNKPM
