<?php if (is_page(20) ){?> <?php } ?>
<?php if( $post->ID == 172) { ?> <?php } ?>

<!------------------- Rating Star ---------------------------->
<div class="rating-star">
<?php 
$rat = get_post_meta($post->ID, 'rating', true); 
for($i=1; $i<=5; $i++){
if($rat>=$i){
echo '<i class="fa fa-star yellow" aria-hidden="true"></i> ';
}
else{
echo '<i class="fa fa-star " aria-hidden="true"></i> ';
}
}
?>           
</div>
<!------------------- After 3 Post Clearfix ---------------------------->
 <?php $i++; if($i==3){ ?> <div class="clearfix"></div> <?php $i=0; } ?>
 
 <!------------------- Default editior ---------------------------->
 add_filter('use_block_editor_for_post', '__return_false');
f