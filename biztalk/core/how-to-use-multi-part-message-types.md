---
title: マルチパート メッセージの種類を使用する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- multi-part message types, parts
- multi-part message types, creating
- multi-part message types, type modifiers
- messages
- multi-part message types, deleting
- orchestrations, messages
- deleting, multi-part messages
- multi-part message types, about multi-part message types
- orchestrations, type modifier
- messages, multi-parts
- creating, multi-part messages
- messages, about messages
ms.assetid: 009a39bd-cfc4-42d9-918c-88ac24bfc370
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4e4a07b88e832d99f586d10cdf8af4dbea3af3e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972080"
---
# <a name="how-to-use-multi-part-message-types"></a><span data-ttu-id="a98b8-102">マルチパート メッセージの種類を使用する方法</span><span class="sxs-lookup"><span data-stu-id="a98b8-102">How to Use Multi-part Message Types</span></span>
<span data-ttu-id="a98b8-103">各メッセージには、マルチパート メッセージの種類、0 個以上のメッセージ部分で構成されるメッセージ構造の記述があります。</span><span class="sxs-lookup"><span data-stu-id="a98b8-103">Each message has a multi-part message type, a description of the message structure that consists of zero or more message parts.</span></span> <span data-ttu-id="a98b8-104">これらの部分は、XSD (XML Schema Definition) 言語スキーマまたは .NET クラスによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="a98b8-104">The parts are defined by XML Schema Definition (XSD) language schemas or .NET classes.</span></span> <span data-ttu-id="a98b8-105">独自のマルチパート メッセージの種類を定義したり、既存の .NET クラスおよびスキーマを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="a98b8-105">You can define your own multi-part message types, or you can use existing .NET classes and schemas.</span></span>  
  
 <span data-ttu-id="a98b8-106">メッセージ部分は、オーケストレーション内で直接アクセスしたり割り当てたりできます。また、識別フィールドまたはプロパティ フィールドとして公開されている、メッセージ部分の各要素を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="a98b8-106">You can access or assign message parts directly within your orchestration, or you can use individual elements of message parts that are exposed as distinguished fields or property fields.</span></span> <span data-ttu-id="a98b8-107">詳細については、次を参照してください。[識別フィールドおよびメッセージ プロパティ](../core/using-distinguished-fields-and-property-fields.md)です。</span><span class="sxs-lookup"><span data-stu-id="a98b8-107">For more information, see [Using Distinguished Fields and Message Properties](../core/using-distinguished-fields-and-property-fields.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a98b8-108">マルチパート メッセージの種類に含める部分は、複数とは限りません。</span><span class="sxs-lookup"><span data-stu-id="a98b8-108">A multi-part message type does not necessarily contain multiple parts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a98b8-109">.NET の型によってメッセージ部分を定義することができます**XmlDocument**を任意の XML ドキュメントを含めるために使用できるし、.NET のある型を XML にシリアル化できる、またはいずれかで .NET カスタム シリアル化をサポートします。</span><span class="sxs-lookup"><span data-stu-id="a98b8-109">A message part can be defined by the .NET type **XmlDocument**, which can be used to contain an arbitrary XML document, by any .NET type that is XML-serializable, or by any .NET type supporting custom serialization.</span></span>  
  
## <a name="add-a-multi-part-message-type"></a><span data-ttu-id="a98b8-110">マルチパート メッセージの種類を追加します。</span><span class="sxs-lookup"><span data-stu-id="a98b8-110">Add a multi-part message type</span></span>  
  
1.  <span data-ttu-id="a98b8-111">**オーケストレーション**ウィンドウで、展開、**型**ノード。</span><span class="sxs-lookup"><span data-stu-id="a98b8-111">In the **Orchestration View** window, expand the **Types** node.</span></span>  
  
2.  <span data-ttu-id="a98b8-112">右クリック**マルチパート メッセージの種類** をクリックし、**新しいマルチパート メッセージの種類**です。</span><span class="sxs-lookup"><span data-stu-id="a98b8-112">Right-click **Multi-part Message Types** and then click **New Multi-part Message Type**.</span></span>  
  
     <span data-ttu-id="a98b8-113">**マルチパート メッセージの種類**が折りたたまれている場合、フォルダーを展開し、1 つの既定のメッセージ部分と共に新しいマルチパート メッセージの種類が追加されます。</span><span class="sxs-lookup"><span data-stu-id="a98b8-113">The **Multi-part Message Types** folder expands, if collapsed, and a new multi-part message type is added with one default message part.</span></span>  
  
3.  <span data-ttu-id="a98b8-114">マルチパート メッセージの種類、および提供されたメッセージ部分に名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="a98b8-114">Name the multi-part message type and the provided message part.</span></span>  
  
     <span data-ttu-id="a98b8-115">名前を割り当てることによって他のパーツを追加するには、マルチパート メッセージの種類は、1 つ以上のメッセージ部分を必要とする場合、\<新規\>メッセージ部分です。</span><span class="sxs-lookup"><span data-stu-id="a98b8-115">If your multi-part message type requires more than one message part, you can add additional parts by assigning a name to the \<New\> message part.</span></span>  
  
4.  <span data-ttu-id="a98b8-116">各メッセージ部分と、.NET クラスまたはスキーマなどの種類を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="a98b8-116">Associate each message part with a type, such as a .NET class or schema.</span></span>  
  
## <a name="remove-a-multi-part-message-type"></a><span data-ttu-id="a98b8-117">マルチパート メッセージの種類を削除します。</span><span class="sxs-lookup"><span data-stu-id="a98b8-117">Remove a multi-part message type</span></span>  
  
-   <span data-ttu-id="a98b8-118">**オーケストレーション**ウィンドウで、右クリックして、マルチパート メッセージの種類を削除し、をクリックする**削除**です。</span><span class="sxs-lookup"><span data-stu-id="a98b8-118">In the **Orchestration View** window, right-click the multi-part message type you want to remove and then click **Delete**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a98b8-119">オーケストレーションからマルチパート メッセージの種類を削除すると、これが使用されているメッセージからも種類の情報が削除されます。</span><span class="sxs-lookup"><span data-stu-id="a98b8-119">Removing a multi-part message type from your orchestration will also remove the type information from messages that use it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a98b8-120">読み取り専用として表示される項目は、別のオーケストレーションで定義されています。</span><span class="sxs-lookup"><span data-stu-id="a98b8-120">Items that appear as read-only are defined in another orchestration.</span></span>  
  
## <a name="remove-a-part-from-a-multi-part-message-type"></a><span data-ttu-id="a98b8-121">マルチパート メッセージの種類から、一部を削除します。</span><span class="sxs-lookup"><span data-stu-id="a98b8-121">Remove a part from a multi-part message type</span></span>  
  
-   <span data-ttu-id="a98b8-122">**オーケストレーションの種類**ウィンドウで、をクリックして削除する部分を右クリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="a98b8-122">In the **Orchestration View** window, right-click the part you want to remove and click **Delete**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a98b8-123">場合は、メッセージの種類のメッセージ部分を削除することはできません、**メッセージのボディ部**プロパティが true に設定します。</span><span class="sxs-lookup"><span data-stu-id="a98b8-123">You cannot delete a message type's message part if the **Message Body Part** property is set to true.</span></span> <span data-ttu-id="a98b8-124">最初に設定する必要があります、**メッセージのボディ部**プロパティをメッセージの種類の部分の別の True です。</span><span class="sxs-lookup"><span data-stu-id="a98b8-124">You must first set the **Message Body Part** property to True for another of the message type's parts.</span></span>  
  
## <a name="set-the-type-modifier-for-a-multi-part-message-type"></a><span data-ttu-id="a98b8-125">マルチパート メッセージの種類に対する型修飾子を設定します。</span><span class="sxs-lookup"><span data-stu-id="a98b8-125">Set the type modifier for a multi-part message type</span></span>  
  
-   <span data-ttu-id="a98b8-126">**プロパティ**ウィンドウでは、次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="a98b8-126">In the **Properties** window, set the following property:</span></span>  
  
    |<span data-ttu-id="a98b8-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a98b8-127">Property</span></span>|<span data-ttu-id="a98b8-128">Description</span><span class="sxs-lookup"><span data-stu-id="a98b8-128">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="a98b8-129">**型修飾子**</span><span class="sxs-lookup"><span data-stu-id="a98b8-129">**Type Modifier**</span></span>|<span data-ttu-id="a98b8-130">マルチパート メッセージの種類のスコープを設定します。</span><span class="sxs-lookup"><span data-stu-id="a98b8-130">Determines the scope of the multi-part message type:</span></span><br /><br /> <span data-ttu-id="a98b8-131">-   **Private-** マルチパート メッセージの種類へのアクセスが含まれているモジュールに制限されます。</span><span class="sxs-lookup"><span data-stu-id="a98b8-131">-   **Private—** Access to this multi-part message type is limited to the containing module.</span></span><br /><span data-ttu-id="a98b8-132">-   **[パブリック]:** マルチパート メッセージの種類へのアクセスは制限されません。</span><span class="sxs-lookup"><span data-stu-id="a98b8-132">-   **Public—** Access to this multi-part message type is not limited.</span></span><br /><span data-ttu-id="a98b8-133">-   **内部 —** マルチパート メッセージの種類へのアクセスは、同じプロジェクト内のモジュールに制限されます。</span><span class="sxs-lookup"><span data-stu-id="a98b8-133">-   **Internal—** Access to this multi-part message type is limited to modules within the same project.</span></span>|  
  
## <a name="add-parts-to-an-existing-multi-part-message"></a><span data-ttu-id="a98b8-134">既存のマルチパート メッセージに部分を追加します。</span><span class="sxs-lookup"><span data-stu-id="a98b8-134">Add parts to an existing multi-part message</span></span>  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="a98b8-135"> では、マルチパート XLANG メッセージに部分を追加できます。また、最初に宣言した部分の数より大きいインデックスによってメッセージ部分 (存在する場合) を参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="a98b8-135"> provides the ability to add parts to a multi part XLANG message and also to refer to a message part by an index greater than the originally declared number of parts if the part exists.</span></span> <span data-ttu-id="a98b8-136">この機能は、可変数の添付ファイルを含んだ SMTP メッセージを送信または受信する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="a98b8-136">This functionality may be useful for sending or receiving SMTP messages with a variable number of attachments.</span></span> <span data-ttu-id="a98b8-137">この機能は、次のように実装されます。</span><span class="sxs-lookup"><span data-stu-id="a98b8-137">This functionality is implemented as follows:</span></span>  
  
-   <span data-ttu-id="a98b8-138">プロジェクトからへの参照を追加**Microsoft.XLANGs.BaseTypes**です。</span><span class="sxs-lookup"><span data-stu-id="a98b8-138">From your project, add a reference to **Microsoft.XLANGs.BaseTypes**.</span></span>  
  
-   <span data-ttu-id="a98b8-139">変数を作成 (たとえば*xlangPart*) 型の**Microsoft.XLANGs.BaseTypes.XLANGMessage**です。</span><span class="sxs-lookup"><span data-stu-id="a98b8-139">Create a variable (for example *xlangPart*) of type **Microsoft.XLANGs.BaseTypes.XLANGMessage**.</span></span>  
  
-   <span data-ttu-id="a98b8-140">呼び出す*xlangPart***です。AddPart(...)** 式図形から適切な引数を使用します。</span><span class="sxs-lookup"><span data-stu-id="a98b8-140">Call *xlangPart***.AddPart(…)** using the appropriate arguments from an Expression shape.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a98b8-141">追加された部分は型**XmlDocument**を使用してカスタムの書式設定されたメッセージ部分を追加することはできませんので、 **AddPart()** メソッドです。</span><span class="sxs-lookup"><span data-stu-id="a98b8-141">The added parts are of type **XmlDocument** so you cannot add a custom formatted message part using the **AddPart()** method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a98b8-142">宣言された部分の数よりも大きい値を含むマルチパート メッセージを受信する場合、オーケストレーション エンジン読み取りの数の部分がありますが、メッセージに作成で宣言されたメッセージ部分の数に一致する部分の適切な部分の種類型と、コンストラクト**XmlDocument**残りの部分の部分です。</span><span class="sxs-lookup"><span data-stu-id="a98b8-142">If a multi part message that contains greater than the number of declared parts is received, the orchestration engine reads how many parts there are in the message, then constructs the proper part types for the parts that match the number of parts in the declared message type and then constructs **XmlDocument** parts for the remaining parts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a98b8-143">参照</span><span class="sxs-lookup"><span data-stu-id="a98b8-143">See Also</span></span>  
 <span data-ttu-id="a98b8-144">**IBaseMessage.AddPart メソッド (COM)**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="a98b8-144">**IBaseMessage.AddPart Method (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>  
 <span data-ttu-id="a98b8-145">[Web 上の XSD リソース](../core/xsd-resources-on-the-web.md) </span><span class="sxs-lookup"><span data-stu-id="a98b8-145">[XSD Resources on the Web](../core/xsd-resources-on-the-web.md) </span></span>  
 <span data-ttu-id="a98b8-146">[識別フィールドおよびプロパティ フィールドの使用](../core/using-distinguished-fields-and-property-fields.md) </span><span class="sxs-lookup"><span data-stu-id="a98b8-146">[Using Distinguished Fields and Property Fields](../core/using-distinguished-fields-and-property-fields.md) </span></span>  
 [<span data-ttu-id="a98b8-147">オーケストレーションでのメッセージの使用</span><span class="sxs-lookup"><span data-stu-id="a98b8-147">Using Messages in Orchestrations</span></span>](../core/using-messages-in-orchestrations.md)