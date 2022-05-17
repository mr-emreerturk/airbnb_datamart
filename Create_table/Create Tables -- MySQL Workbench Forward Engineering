-- MySQL Workbench Forward Engineering

SET @OLD_UNIQUE_CHECKS=@@UNIQUE_CHECKS, UNIQUE_CHECKS=0;
SET @OLD_FOREIGN_KEY_CHECKS=@@FOREIGN_KEY_CHECKS, FOREIGN_KEY_CHECKS=0;
SET @OLD_SQL_MODE=@@SQL_MODE, SQL_MODE='ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION';

-- -----------------------------------------------------
-- Schema mydb
-- -----------------------------------------------------
-- -----------------------------------------------------
-- Schema Airbnb
-- -----------------------------------------------------

-- -----------------------------------------------------
-- Schema Airbnb
-- -----------------------------------------------------
CREATE SCHEMA IF NOT EXISTS `Airbnb` DEFAULT CHARACTER SET utf8 ;
USE `Airbnb` ;

-- -----------------------------------------------------
-- Table `Airbnb`.`country`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `Airbnb`.`country` ;

CREATE TABLE IF NOT EXISTS `Airbnb`.`country` (
  `country_code` VARCHAR(3) NOT NULL,
  `name` VARCHAR(45) NULL DEFAULT NULL,
  PRIMARY KEY (`country_code`))
ENGINE = InnoDB
DEFAULT CHARACTER SET = utf8mb3;


-- -----------------------------------------------------
-- Table `Airbnb`.`city`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `Airbnb`.`city` ;

CREATE TABLE IF NOT EXISTS `Airbnb`.`city` (
  `city_id` INT NOT NULL AUTO_INCREMENT,
  `name` VARCHAR(45) NOT NULL,
  `country_code` VARCHAR(3) NOT NULL,
  PRIMARY KEY (`city_id`),
  INDEX `fk_city_country_idx` (`country_code` ASC) VISIBLE,
  CONSTRAINT `fk_city_country`
    FOREIGN KEY (`country_code`)
    REFERENCES `Airbnb`.`country` (`country_code`)
    ON DELETE CASCADE
    ON UPDATE CASCADE)
ENGINE = InnoDB
AUTO_INCREMENT = 23
DEFAULT CHARACTER SET = utf8mb3;


-- -----------------------------------------------------
-- Table `Airbnb`.`neighborhood`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `Airbnb`.`neighborhood` ;

CREATE TABLE IF NOT EXISTS `Airbnb`.`neighborhood` (
  `neighborhood_id` INT NOT NULL AUTO_INCREMENT,
  `name` VARCHAR(45) NOT NULL,
  `city_id` INT NULL DEFAULT NULL,
  `country_code` VARCHAR(3) NULL DEFAULT NULL,
  PRIMARY KEY (`neighborhood_id`),
  INDEX `fk_neighborhood_city1_idx` (`city_id` ASC) VISIBLE,
  INDEX `fk_country_idx` (`country_code` ASC) VISIBLE,
  CONSTRAINT `fk_country`
    FOREIGN KEY (`country_code`)
    REFERENCES `Airbnb`.`country` (`country_code`)
    ON DELETE CASCADE
    ON UPDATE CASCADE,
  CONSTRAINT `fk_neighborhood_city1`
    FOREIGN KEY (`city_id`)
    REFERENCES `Airbnb`.`city` (`city_id`))
ENGINE = InnoDB
AUTO_INCREMENT = 21
DEFAULT CHARACTER SET = utf8mb3;


-- -----------------------------------------------------
-- Table `Airbnb`.`coordintates`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `Airbnb`.`coordintates` ;

CREATE TABLE IF NOT EXISTS `Airbnb`.`coordintates` (
  `coordintates_id` INT NOT NULL AUTO_INCREMENT,
  `longitude` DECIMAL(9,6) NOT NULL,
  `latitude` DECIMAL(8,6) NOT NULL,
  PRIMARY KEY (`coordintates_id`))
ENGINE = InnoDB
AUTO_INCREMENT = 21
DEFAULT CHARACTER SET = utf8mb3;


-- -----------------------------------------------------
-- Table `Airbnb`.`address`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `Airbnb`.`address` ;

CREATE TABLE IF NOT EXISTS `Airbnb`.`address` (
  `address_id` INT NOT NULL AUTO_INCREMENT,
  `country_code` VARCHAR(3) NOT NULL,
  `city_id` INT NOT NULL,
  `neighborhood_id` INT NOT NULL,
  `street` VARCHAR(90) NOT NULL,
  `housenumber` INT NOT NULL,
  `apartmentnumber` INT NULL DEFAULT NULL,
  `coordintates_id` INT NOT NULL,
  PRIMARY KEY (`address_id`),
  INDEX `fk_idx` (`country_code` ASC) VISIBLE,
  INDEX `fk3_idx` (`neighborhood_id` ASC) VISIBLE,
  INDEX `fk4_idx` (`coordintates_id` ASC) VISIBLE,
  INDEX `fk2_idx` (`city_id` ASC) VISIBLE,
  CONSTRAINT `fk`
    FOREIGN KEY (`country_code`)
    REFERENCES `Airbnb`.`country` (`country_code`)
    ON DELETE CASCADE
    ON UPDATE CASCADE,
  CONSTRAINT `fk2`
    FOREIGN KEY (`city_id`)
    REFERENCES `Airbnb`.`city` (`city_id`)
    ON DELETE CASCADE
    ON UPDATE CASCADE,
  CONSTRAINT `fk3`
    FOREIGN KEY (`neighborhood_id`)
    REFERENCES `Airbnb`.`neighborhood` (`neighborhood_id`)
    ON DELETE CASCADE
    ON UPDATE CASCADE,
  CONSTRAINT `fk4`
    FOREIGN KEY (`coordintates_id`)
    REFERENCES `Airbnb`.`coordintates` (`coordintates_id`)
    ON DELETE CASCADE
    ON UPDATE CASCADE)
ENGINE = InnoDB
AUTO_INCREMENT = 21
DEFAULT CHARACTER SET = utf8mb3;


-- -----------------------------------------------------
-- Table `Airbnb`.`amenities`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `Airbnb`.`amenities` ;

CREATE TABLE IF NOT EXISTS `Airbnb`.`amenities` (
  `amenities_id` INT NOT NULL AUTO_INCREMENT,
  `wifi` TINYINT NULL DEFAULT NULL,
  `kitchen` TINYINT NULL DEFAULT NULL,
  `washer` TINYINT NULL DEFAULT NULL,
  `dryer` TINYINT NULL DEFAULT NULL,
  `ac` TINYINT NULL DEFAULT NULL,
  `heating` TINYINT NULL DEFAULT NULL,
  `workspace` TINYINT NULL DEFAULT NULL,
  `tv` TINYINT NULL DEFAULT NULL,
  `hairdryer` TINYINT NULL DEFAULT NULL,
  `iron` TINYINT NULL DEFAULT NULL,
  `pool` TINYINT NULL DEFAULT NULL,
  `hottub` TINYINT NULL DEFAULT NULL,
  `parking` TINYINT NULL DEFAULT NULL,
  `ev_charger` TINYINT NULL DEFAULT NULL,
  `gym` TINYINT NULL DEFAULT NULL,
  `breakfast` TINYINT NULL DEFAULT NULL,
  `indoor_fireplace` TINYINT NULL DEFAULT NULL,
  `smoking_allowed` TINYINT NULL DEFAULT NULL,
  `waterfront` TINYINT NULL DEFAULT NULL,
  `smoke_alarm` TINYINT NULL DEFAULT NULL,
  `carbonmonoxide_alarm` TINYINT NULL DEFAULT NULL,
  PRIMARY KEY (`amenities_id`))
ENGINE = InnoDB
AUTO_INCREMENT = 21
DEFAULT CHARACTER SET = utf8mb3;


-- -----------------------------------------------------
-- Table `Airbnb`.`social_media`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `Airbnb`.`social_media` ;

CREATE TABLE IF NOT EXISTS `Airbnb`.`social_media` (
  `social_media_id` INT NOT NULL AUTO_INCREMENT,
  `facebook` VARCHAR(100) NULL DEFAULT NULL,
  `instagram` VARCHAR(100) NULL DEFAULT NULL,
  `twitter` VARCHAR(100) NULL DEFAULT NULL,
  PRIMARY KEY (`social_media_id`))
ENGINE = InnoDB
AUTO_INCREMENT = 21
DEFAULT CHARACTER SET = utf8mb3;


-- -----------------------------------------------------
-- Table `Airbnb`.`language`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `Airbnb`.`language` ;

CREATE TABLE IF NOT EXISTS `Airbnb`.`language` (
  `language` VARCHAR(45) NOT NULL,
  PRIMARY KEY (`language`))
ENGINE = InnoDB
DEFAULT CHARACTER SET = utf8mb3;


-- -----------------------------------------------------
-- Table `Airbnb`.`user`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `Airbnb`.`user` ;

CREATE TABLE IF NOT EXISTS `Airbnb`.`user` (
  `user_id` INT NOT NULL AUTO_INCREMENT,
  `first_name` VARCHAR(45) NOT NULL,
  `last_name` VARCHAR(45) NOT NULL,
  `gender` VARCHAR(45) NOT NULL,
  `password` VARCHAR(45) NOT NULL,
  `email` VARCHAR(45) NOT NULL,
  `phone` VARCHAR(45) NULL DEFAULT NULL,
  `user_type` VARCHAR(1) NOT NULL,
  `language` VARCHAR(45) NULL DEFAULT 'english',
  `social_media_id` INT NULL DEFAULT '1',
  PRIMARY KEY (`user_id`),
  INDEX `fk_user_social_media1_idx` (`social_media_id` ASC) VISIBLE,
  INDEX `language_idx` (`language` ASC) VISIBLE,
  CONSTRAINT `fk_user_social_media1`
    FOREIGN KEY (`social_media_id`)
    REFERENCES `Airbnb`.`social_media` (`social_media_id`),
  CONSTRAINT `language`
    FOREIGN KEY (`language`)
    REFERENCES `Airbnb`.`language` (`language`)
    ON DELETE CASCADE
    ON UPDATE CASCADE)
ENGINE = InnoDB
AUTO_INCREMENT = 31
DEFAULT CHARACTER SET = utf8mb3;


-- -----------------------------------------------------
-- Table `Airbnb`.`review_rating`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `Airbnb`.`review_rating` ;

CREATE TABLE IF NOT EXISTS `Airbnb`.`review_rating` (
  `review_rating_id` INT NOT NULL AUTO_INCREMENT,
  `review` VARCHAR(500) NULL DEFAULT NULL,
  `rating` INT NULL DEFAULT NULL,
  `date_reviewed` DATETIME NULL DEFAULT NULL,
  `user_id` INT NOT NULL,
  `property_id` INT NOT NULL,
  PRIMARY KEY (`review_rating_id`),
  INDEX `fk_review_rating_user1_idx` (`user_id` ASC) VISIBLE,
  INDEX `fk_review_rating_property1_idx` (`property_id` ASC) VISIBLE,
  CONSTRAINT `fk_review_rating_property1`
    FOREIGN KEY (`property_id`)
    REFERENCES `Airbnb`.`property` (`property_id`)
    ON DELETE CASCADE
    ON UPDATE CASCADE,
  CONSTRAINT `fk_review_rating_user1`
    FOREIGN KEY (`user_id`)
    REFERENCES `Airbnb`.`user` (`user_id`)
    ON DELETE CASCADE
    ON UPDATE CASCADE)
ENGINE = InnoDB
AUTO_INCREMENT = 51
DEFAULT CHARACTER SET = utf8mb3;


-- -----------------------------------------------------
-- Table `Airbnb`.`rooms_beds`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `Airbnb`.`rooms_beds` ;

CREATE TABLE IF NOT EXISTS `Airbnb`.`rooms_beds` (
  `rooms_beds_id` INT NOT NULL AUTO_INCREMENT,
  `bedrooms` INT NULL DEFAULT NULL,
  `beds` INT NOT NULL,
  `bathrooms` INT NULL DEFAULT NULL,
  PRIMARY KEY (`rooms_beds_id`))
ENGINE = InnoDB
AUTO_INCREMENT = 21
DEFAULT CHARACTER SET = utf8mb3;


-- -----------------------------------------------------
-- Table `Airbnb`.`type_of_place`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `Airbnb`.`type_of_place` ;

CREATE TABLE IF NOT EXISTS `Airbnb`.`type_of_place` (
  `type_of_place_id` INT NOT NULL AUTO_INCREMENT,
  `type_of_place` ENUM('apartment', 'room', 'bed', 'hotel') NULL DEFAULT NULL,
  PRIMARY KEY (`type_of_place_id`))
ENGINE = InnoDB
AUTO_INCREMENT = 21
DEFAULT CHARACTER SET = utf8mb3;


-- -----------------------------------------------------
-- Table `Airbnb`.`property`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `Airbnb`.`property` ;

CREATE TABLE IF NOT EXISTS `Airbnb`.`property` (
  `property_id` INT NOT NULL AUTO_INCREMENT,
  `title` VARCHAR(45) NOT NULL,
  `date_created` DATETIME NULL DEFAULT NULL,
  `address_id` INT NOT NULL,
  `user_id` INT NOT NULL,
  `review_rating_id` INT NULL DEFAULT NULL,
  INDEX `fk_property_address1_idx` (`address_id` ASC) VISIBLE,
  INDEX `fk_property_user1_idx` (`user_id` ASC) VISIBLE,
  INDEX `fk_property_review_rating_1_idx` (`review_rating_id` ASC) VISIBLE,
  INDEX `fl_property_amenities_idx` (`property_id` ASC) VISIBLE,
  CONSTRAINT `fk_property_address1`
    FOREIGN KEY (`address_id`)
    REFERENCES `Airbnb`.`address` (`address_id`)
    ON DELETE CASCADE
    ON UPDATE CASCADE,
  CONSTRAINT `fk_property_review_rating_1`
    FOREIGN KEY (`review_rating_id`)
    REFERENCES `Airbnb`.`review_rating` (`property_id`)
    ON DELETE CASCADE
    ON UPDATE CASCADE,
  CONSTRAINT `fk_property_rooms_beds_1`
    FOREIGN KEY (`property_id`)
    REFERENCES `Airbnb`.`rooms_beds` (`rooms_beds_id`)
    ON DELETE CASCADE
    ON UPDATE CASCADE,
  CONSTRAINT `fk_property_type_of_place1`
    FOREIGN KEY (`property_id`)
    REFERENCES `Airbnb`.`type_of_place` (`type_of_place_id`)
    ON DELETE CASCADE
    ON UPDATE CASCADE,
  CONSTRAINT `fk_property_user1`
    FOREIGN KEY (`user_id`)
    REFERENCES `Airbnb`.`user` (`user_id`)
    ON DELETE CASCADE
    ON UPDATE CASCADE,
  CONSTRAINT `fl_property_amenities`
    FOREIGN KEY (`property_id`)
    REFERENCES `Airbnb`.`amenities` (`amenities_id`)
    ON DELETE CASCADE
    ON UPDATE CASCADE)
ENGINE = InnoDB
AUTO_INCREMENT = 21
DEFAULT CHARACTER SET = utf8mb3;


-- -----------------------------------------------------
-- Table `Airbnb`.`booking`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `Airbnb`.`booking` ;

CREATE TABLE IF NOT EXISTS `Airbnb`.`booking` (
  `booking_id` INT NOT NULL AUTO_INCREMENT,
  `check_in` DATE NOT NULL,
  `check_out` DATE NOT NULL,
  `number_guests` INT NOT NULL,
  `property_id` INT NOT NULL,
  `user_id` INT NOT NULL,
  PRIMARY KEY (`booking_id`),
  INDEX `fk_booking_property1_idx` (`property_id` ASC) VISIBLE,
  INDEX `fk_booking_user1_idx` (`user_id` ASC) VISIBLE,
  CONSTRAINT `fk_booking_property1`
    FOREIGN KEY (`property_id`)
    REFERENCES `Airbnb`.`property` (`property_id`)
    ON DELETE CASCADE
    ON UPDATE CASCADE,
  CONSTRAINT `fk_booking_user1`
    FOREIGN KEY (`user_id`)
    REFERENCES `Airbnb`.`user` (`user_id`)
    ON DELETE CASCADE
    ON UPDATE CASCADE)
ENGINE = InnoDB
AUTO_INCREMENT = 21
DEFAULT CHARACTER SET = utf8mb3;


-- -----------------------------------------------------
-- Table `Airbnb`.`images`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `Airbnb`.`images` ;

CREATE TABLE IF NOT EXISTS `Airbnb`.`images` (
  `images_id` INT NOT NULL AUTO_INCREMENT,
  `image` VARCHAR(10) NULL DEFAULT 'file.jpg',
  `description` VARCHAR(100) NULL DEFAULT NULL,
  `property_id` INT NULL DEFAULT NULL,
  PRIMARY KEY (`images_id`),
  INDEX `fk_images_property_1_idx` (`property_id` ASC) VISIBLE,
  CONSTRAINT `fk_images_property_1`
    FOREIGN KEY (`property_id`)
    REFERENCES `Airbnb`.`property` (`property_id`)
    ON DELETE CASCADE
    ON UPDATE CASCADE)
ENGINE = InnoDB
AUTO_INCREMENT = 51
DEFAULT CHARACTER SET = utf8mb3;


-- -----------------------------------------------------
-- Table `Airbnb`.`messages`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `Airbnb`.`messages` ;

CREATE TABLE IF NOT EXISTS `Airbnb`.`messages` (
  `messages_id` INT NOT NULL AUTO_INCREMENT,
  `content` VARCHAR(500) NULL DEFAULT NULL,
  `sender` INT NULL DEFAULT NULL,
  `receiver` INT NULL DEFAULT NULL,
  PRIMARY KEY (`messages_id`),
  INDEX `sender_idx` (`sender` ASC) VISIBLE,
  INDEX `receiver_idx` (`receiver` ASC) VISIBLE,
  CONSTRAINT `receiver`
    FOREIGN KEY (`receiver`)
    REFERENCES `Airbnb`.`user` (`user_id`)
    ON DELETE CASCADE
    ON UPDATE CASCADE,
  CONSTRAINT `sender`
    FOREIGN KEY (`sender`)
    REFERENCES `Airbnb`.`user` (`user_id`)
    ON DELETE CASCADE
    ON UPDATE CASCADE)
ENGINE = InnoDB
AUTO_INCREMENT = 26
DEFAULT CHARACTER SET = utf8mb3;


-- -----------------------------------------------------
-- Table `Airbnb`.`number_guests`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `Airbnb`.`number_guests` ;

CREATE TABLE IF NOT EXISTS `Airbnb`.`number_guests` (
  `number_guests_id` INT NOT NULL AUTO_INCREMENT,
  `adults` INT NOT NULL,
  `children` INT NULL DEFAULT NULL,
  `babies` INT NULL DEFAULT NULL,
  `pets` INT NULL DEFAULT NULL,
  CONSTRAINT `fk_number_of_guests_property`
    FOREIGN KEY (`number_guests_id`)
    REFERENCES `Airbnb`.`property` (`property_id`)
    ON DELETE CASCADE
    ON UPDATE CASCADE)
ENGINE = InnoDB
AUTO_INCREMENT = 21
DEFAULT CHARACTER SET = utf8mb3;


-- -----------------------------------------------------
-- Table `Airbnb`.`payment_method`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `Airbnb`.`payment_method` ;

CREATE TABLE IF NOT EXISTS `Airbnb`.`payment_method` (
  `payment_method_id` INT NOT NULL AUTO_INCREMENT,
  `payment_method` VARCHAR(45) NULL DEFAULT NULL,
  PRIMARY KEY (`payment_method_id`),
  CONSTRAINT `fk_paymentmethod_user_1`
    FOREIGN KEY (`payment_method_id`)
    REFERENCES `Airbnb`.`user` (`user_id`)
    ON DELETE CASCADE
    ON UPDATE CASCADE)
ENGINE = InnoDB
AUTO_INCREMENT = 21
DEFAULT CHARACTER SET = utf8mb3;


-- -----------------------------------------------------
-- Table `Airbnb`.`price`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `Airbnb`.`price` ;

CREATE TABLE IF NOT EXISTS `Airbnb`.`price` (
  `price_id` INT NOT NULL AUTO_INCREMENT,
  `base_price` INT NULL DEFAULT NULL,
  `discount_per_week` INT NULL DEFAULT NULL,
  `discount_per_month` INT NULL DEFAULT NULL,
  `service_fee` INT NULL DEFAULT NULL,
  `airbnb_fee` INT NULL DEFAULT NULL,
  CONSTRAINT `fk_price_property_1`
    FOREIGN KEY (`price_id`)
    REFERENCES `Airbnb`.`property` (`property_id`)
    ON DELETE CASCADE
    ON UPDATE CASCADE)
ENGINE = InnoDB
AUTO_INCREMENT = 21
DEFAULT CHARACTER SET = utf8mb3;


-- -----------------------------------------------------
-- Table `Airbnb`.`wishlist`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `Airbnb`.`wishlist` ;

CREATE TABLE IF NOT EXISTS `Airbnb`.`wishlist` (
  `wishlist_id` INT NOT NULL AUTO_INCREMENT,
  `name` VARCHAR(45) NOT NULL,
  `user_id` INT NOT NULL,
  PRIMARY KEY (`wishlist_id`),
  INDEX `fk_wishlist_user1_idx` (`user_id` ASC) VISIBLE,
  CONSTRAINT `fk_wishlist_user1`
    FOREIGN KEY (`user_id`)
    REFERENCES `Airbnb`.`user` (`user_id`))
ENGINE = InnoDB
AUTO_INCREMENT = 21
DEFAULT CHARACTER SET = utf8mb3;


-- -----------------------------------------------------
-- Table `Airbnb`.`wishlist_has_property`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `Airbnb`.`wishlist_has_property` ;

CREATE TABLE IF NOT EXISTS `Airbnb`.`wishlist_has_property` (
  `wishlist_id` INT NOT NULL,
  `property_id` INT NOT NULL,
  PRIMARY KEY (`wishlist_id`, `property_id`),
  INDEX `fk_wishlist_has_property_property1_idx` (`property_id` ASC) VISIBLE,
  INDEX `fk_wishlist_has_property_wishlist1_idx` (`wishlist_id` ASC) VISIBLE,
  CONSTRAINT `fk_wishlist_has_property_property1`
    FOREIGN KEY (`property_id`)
    REFERENCES `Airbnb`.`property` (`property_id`)
    ON DELETE CASCADE
    ON UPDATE CASCADE,
  CONSTRAINT `fk_wishlist_has_property_wishlist1`
    FOREIGN KEY (`wishlist_id`)
    REFERENCES `Airbnb`.`wishlist` (`wishlist_id`)
    ON DELETE CASCADE
    ON UPDATE CASCADE)
ENGINE = InnoDB
DEFAULT CHARACTER SET = utf8mb3;


SET SQL_MODE=@OLD_SQL_MODE;
SET FOREIGN_KEY_CHECKS=@OLD_FOREIGN_KEY_CHECKS;
SET UNIQUE_CHECKS=@OLD_UNIQUE_CHECKS;
