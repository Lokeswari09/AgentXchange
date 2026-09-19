# AgentXchange
# AgentXchange: AI-Powered Product Matching and Negotiation

## Implementation

AgentXchange is implemented as an AI-powered multi-agent marketplace that connects buyers with multiple independent seller agents. The system understands buyer requirements, searches seller inventories, validates product constraints, compares available offers, and supports AI-assisted negotiation.

### System Workflow

```text
Buyer
  ↓
Conversational Interface
  ↓
Buyer Agent
  ↓
Requirement Extraction
  ↓
Structured Constraints
  ↓
Multiple Seller Agents
  ↓
Seller Inventories / APIs
  ↓
Product Fusion
  ↓
Constraint Validation
  ↓
Ranking Agent
  ↓
Offer Comparison
  ↓
Buyer Selects Offer
  ↓
Negotiation Agent
  ↓
Final Offer
```

### 1. Buyer Interface

The buyer interacts with the system through a conversational interface and provides product requirements using natural language.

**Example:**

> I need a Lenovo laptop under ₹70,000 with 16GB RAM, 512GB SSD and delivery within 5 days.

The request is forwarded to the Buyer Agent for requirement extraction.

### 2. Buyer Agent

The Buyer Agent processes the natural-language query and converts it into structured product requirements.

**Example:**

```json
{
  "category": "Laptop",
  "brand": "Lenovo",
  "max_price": 70000,
  "ram": "16GB",
  "storage": "512GB",
  "delivery_days": 5
}
```

### 3. Seller Agents

Each seller is represented by an independent Seller Agent connected to the seller's inventory and business information.

Seller information includes:

- Product details
- Price
- Stock
- Warranty
- Delivery time
- Seller reliability
- Minimum price
- Discount limits

Multiple Seller Agents independently process the buyer's requirements.

### 4. Product Retrieval

The Buyer Agent sends the structured requirements to multiple Seller Agents. Each agent searches its respective inventory and returns relevant products.

The system can use authorized seller APIs, marketplace APIs/feeds, or participating seller inventories.

### 5. Product Fusion

Products retrieved from multiple sellers are combined into a unified result set. This allows similar products from different sellers to be compared in one place.

### 6. Constraint Validation

The Constraint Validator checks whether the retrieved products satisfy the buyer's requirements.

**Example:**

```text
Price ≤ ₹70,000       ✓
RAM ≥ 16GB            ✓
Storage ≥ 512GB       ✓
Delivery ≤ 5 days     ✓
Warranty Requirement  ✓
```

Products that do not satisfy the required constraints are filtered out.

### 7. Ranking and Comparison

The Ranking Agent evaluates the valid offers based on multiple factors, including:

- Price
- Product specifications
- Stock availability
- Warranty
- Delivery time
- Seller reliability

The verified offers are then displayed through a unified comparison interface.

### 8. AI-Assisted Negotiation

After selecting a suitable product and seller, the buyer can initiate the negotiation process.

The Negotiation Agent communicates with the selected Seller Agent based on predefined seller rules such as:

```text
Minimum Price
Maximum Discount
Available Stock
Minimum Order Quantity
Delivery Capability
```

The agents can exchange offers and counteroffers until an agreement is reached or the negotiation is terminated.

### 9. Final Offer

After successful negotiation, the system presents the final offer to the buyer.

The final offer contains:

- Product
- Seller
- Quantity
- Original price
- Negotiated price
- Warranty
- Delivery information
- Final terms

### 10. Scalability

The architecture allows new sellers to be added through additional Seller Agents connected to their inventories or APIs. This enables the system to support multiple sellers and large product inventories while maintaining independent seller business rules.
