
class Product {
    private String idProduct;
    private String nameProduct;
    private Categories Category;

    public Product(Product product) {
        this(product.getIdProduct(), product.getNameProduct(), new Categories(product.getCategory()));
    }

    public Product(String idProduct, String nameProduct, Categories category) {
        this.idProduct = idProduct;
        this.nameProduct = nameProduct;
        this.Category = category;
    }

    public Product(String idProduct, String nameProduct, String category) {
    }

    public Object clone() {
        Product product = null;
        try {
            product = (Product) super.clone();
        } catch (CloneNotSupportedException e) {
            product = new Product(
                    this.getIdProduct(), this.getNameProduct(), this.getCategory());
        }
        product.Category =(Categories) this.Category.clone();
        return product;
    }

    public String getIdProduct() {
        return idProduct;
    }

    public void setIdProduct(String idProduct) {
        this.idProduct = idProduct;
    }

    public String getNameProduct() {
        return nameProduct;
    }

    public void setNameProduct(String nameProduct) {
        this.nameProduct = nameProduct;
    }

    public static String getCategory() {
        return Category() ;
    }

    private static String Category() {

        return null;
    }

    public void setCategory(String category) {
        this.Category = Category;
    }

    @Override
    public String toString() {
        return "Product{" +
                "idProduct='" + idProduct + '\'' +
                ", nameProduct='" + nameProduct + '\'' +
                ", category=" + Category + '\'' +
                '}';
    }

    public void setFirstName(String reni) {
    }

    public void setnameCatt(String gadget) {
    }
}

class Categories {
    private String idCatt;
    private String nameCatt;


    public Categories(String idCatt, String nameCatt) {
        this.idCatt = idCatt;
        this.nameCatt = nameCatt;
    }

    public Categories() {
    }

    public Categories(String category) {
    }

    public Object clone() {
        try {
            return (Categories) super.clone();
        } catch (CloneNotSupportedException e) {
            return new Categories(this.getIdCatt(), this.getNameCatt());
        }
    }

    public String getIdCatt() {
        return idCatt;
    }

    public void setIdCatt(String idCatt) {
        this.idCatt = idCatt;
    }

    public String getNameCatt() {
        return nameCatt;
    }

    public void getNameCatt(String nameCatt) {
        this.nameCatt = nameCatt;
    }

    @Override
    public String toString() {
        return "Categories{" +
                "id='" + idCatt + '\'' +
                ", Name='" + nameCatt + '\'' +
                '}';
    }
}

class deepCopy {
    public static void main(String args[]) {
        deepCopy main = new deepCopy();
        main.product1();
    }

    public void product1() {
        Categories categories = new Categories("c01", "Gadget");
        Product laptop = new Product("p01", "Handphone", new Categories ());
        Product Smartphone = (Product) laptop.clone();

        Smartphone.setnameCatt("Gadget");
        Smartphone.setFirstName("Reni");

        System.out.println(laptop);
        System.out.println(Smartphone);
    }
}
