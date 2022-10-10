# CV Markdown task

## Piotr Szymaniec
### mobile: +48 345 678 901
### email: [piotr.szymaniec@gmail.com](email:piotr.szymaniec@mail.com)
### linked-in: linked.in/com
---
### career goals
I'm open minded, friendly and curious person. My goal is to build up frontend development skill-set to join interesting projects and help my future team mates to the best of my abilities. Id like to grow as programmer and as a person with help of passionate programming enthusiasts. I look forward to working with you!
---
### Skills
Javascript, css, html
git/github, VSC, Windows/MacOS, gitkraken, Photoshop
### Education
Warsaw University of Science and Technology
Comprehensive Javascript 9 week course
Code Reading Club - programmers monthly meetings in english developing code comprehension and analysis

### Languages
- Polish
- English

### Code sample
```ts
import Signal from '../../common/signal';

const Items = [
  { type:'🍃', points: 0},
  { type:'💰', points: 10},
  { type:'🎁', points: 30},
  { type:'💎', points: 50},
]

export interface IItem {
  type: string;
  points: number;
}

export default class Tile {
  content: string
  item: IItem
  visited: boolean
  onVisit: Signal<void> = new Signal()

  constructor() {
    this.content  = "🌲"
    this.visited = false
    this.item = this.generateItem(Items)
  }

  getPoints():number {
    return this.item.points
  }
  getAppearance():string {
    return this.item.type
  }

  generateItem(itemsList:Array<IItem>):IItem {
    const item =  itemsList[Math.floor(Math.random()*itemsList.length)]
    return item
  }

  visit() {
    if (this.visited === false) {
      this.visited = true
      this.content = this.getAppearance()
      this.onVisit.emit()
    }
  }
}
```