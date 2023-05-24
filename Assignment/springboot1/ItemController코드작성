package likelion.springbootzzanggu2.controller;

import likelion.springbootzzanggu2.domain.Item;
import likelion.springbootzzanggu2.service.ItemService;
import likelion.springbootzzanggu2.service.ItemServiceImpl;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.PostMapping;
import org.springframework.web.bind.annotation.RequestMapping;

import java.util.List;

@Controller
@RequestMapping("items")
public class ItemController {
    private final ItemService itemService;

    @Autowired
    public ItemController(ItemServiceImpl itemServiceImpl) {
        this.itemService = itemServiceImpl;
    }

    @GetMapping("new")
    public String createForm(Model model) {
        model.addAttribute("itemForm", new Item());
        return "items/createItemForm";
    }

    @PostMapping("new")
    public String create(Item item) {
        itemService.save(item);
        return "redirect:/";
    }

    @GetMapping("")
    public String findAll(Model model) {
        List<Item> itemList = itemService.findAll();
        model.addAttribute("itemList", itemList);
        return "items/itemList";
    }



}
