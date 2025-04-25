<div class="card">
    <div class="card-body row">
       <div class="card-title h3 col-8">Edit Data Books </div>
       <div class="col-4 mb-2">
            <a href="?em=ujianawal&s=view" class="btn btn-md btn-primary float-end">Back</a>
       </div>
       
        <?php
        include_once "setting.php";
        $id = $_GET['id'];
        $sql = "SELECT * FROM ujianawal WHERE id='$id'";
        $query = mysqli_query($koneksi, $sql);
        $r = mysqli_fetch_array($query);
        ?>
       <form action="?em=ujianawal&s=update" method="post">
        <div class="mb-2">
            <input type="text" class="form-control" name="title" value="<?php echo $r['title'] ?>" placeholder="title" required>
        </div>
        <div class="mb-2">
            <input type="text" class="form-control" name="author" value="<?php echo $r['author'] ?>"  placeholder="author">
        </div>
        <div class="mb-2">
            <input type="text" class="form-control" name="publisher" value="<?php echo $r['publisher'] ?>"  placeholder="publisher">
        </div>
        <div class="mb-2">
            <input type="number" class="form-control" name="year" value="<?php echo $r['year'] ?>"  placeholder="year">
        </div>
        <div class="mb-2">
            <input type="hidden" name="id" value="<?= $r['id']; ?>">
            <input type="reset" class="btn btn-sm btn-danger">
            <input type="submit" class="btn btn-sm btn-primary" name="update" value="Update" >
        </div>

       </form>
    </div>
</div>
