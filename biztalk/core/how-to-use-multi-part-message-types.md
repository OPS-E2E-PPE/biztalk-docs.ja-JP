---
title: マルチパート メッセージの種類を使用する方法 |Microsoft Docs
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
ms.openlocfilehash: 083746c38a175db840f4554297e86d26b5fcb366
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013947"
---
# <a name="how-to-use-multi-part-message-types"></a><span data-ttu-id="208dd-102">マルチパート メッセージの種類を使用する方法</span><span class="sxs-lookup"><span data-stu-id="208dd-102">How to Use Multi-part Message Types</span></span>
<span data-ttu-id="208dd-103">各メッセージには、マルチパート メッセージの種類、0 個以上のメッセージ部分で構成されるメッセージ構造の記述があります。</span><span class="sxs-lookup"><span data-stu-id="208dd-103">Each message has a multi-part message type, a description of the message structure that consists of zero or more message parts.</span></span> <span data-ttu-id="208dd-104">これらの部分は、XSD (XML Schema Definition) 言語スキーマまたは .NET クラスによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="208dd-104">The parts are defined by XML Schema Definition (XSD) language schemas or .NET classes.</span></span> <span data-ttu-id="208dd-105">独自のマルチパート メッセージの種類を定義したり、既存の .NET クラスおよびスキーマを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="208dd-105">You can define your own multi-part message types, or you can use existing .NET classes and schemas.</span></span>  

 <span data-ttu-id="208dd-106">メッセージ部分は、オーケストレーション内で直接アクセスしたり割り当てたりできます。また、識別フィールドまたはプロパティ フィールドとして公開されている、メッセージ部分の各要素を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="208dd-106">You can access or assign message parts directly within your orchestration, or you can use individual elements of message parts that are exposed as distinguished fields or property fields.</span></span> <span data-ttu-id="208dd-107">詳細については、[識別フィールドおよびメッセージ プロパティ](../core/using-distinguished-fields-and-property-fields.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="208dd-107">For more information, see [Using Distinguished Fields and Message Properties](../core/using-distinguished-fields-and-property-fields.md).</span></span>  

> [!NOTE]
>  <span data-ttu-id="208dd-108">マルチパート メッセージの種類に含める部分は、複数とは限りません。</span><span class="sxs-lookup"><span data-stu-id="208dd-108">A multi-part message type does not necessarily contain multiple parts.</span></span>  

> [!NOTE]
>  <span data-ttu-id="208dd-109">メッセージ部分は、.NET 型で定義できます**XmlDocument**を任意の XML ドキュメントを含めるために使用できますし、XML のシリアル化できる任意の .NET 型またはいずれかで .NET カスタム シリアル化のサポート。</span><span class="sxs-lookup"><span data-stu-id="208dd-109">A message part can be defined by the .NET type **XmlDocument**, which can be used to contain an arbitrary XML document, by any .NET type that is XML-serializable, or by any .NET type supporting custom serialization.</span></span>  

## <a name="add-a-multi-part-message-type"></a><span data-ttu-id="208dd-110">マルチパート メッセージの種類を追加します。</span><span class="sxs-lookup"><span data-stu-id="208dd-110">Add a multi-part message type</span></span>  

1.  <span data-ttu-id="208dd-111">**オーケストレーション**ウィンドウで、展開、**型**ノード。</span><span class="sxs-lookup"><span data-stu-id="208dd-111">In the **Orchestration View** window, expand the **Types** node.</span></span>  

2.  <span data-ttu-id="208dd-112">右クリックして**マルチパート メッセージの種類** をクリックし、**新しいマルチパート メッセージの種類**します。</span><span class="sxs-lookup"><span data-stu-id="208dd-112">Right-click **Multi-part Message Types** and then click **New Multi-part Message Type**.</span></span>  

     <span data-ttu-id="208dd-113">**マルチパート メッセージの種類**が折りたたまれている場合、フォルダーを展開され、1 つの既定のメッセージ部分と共に新しいマルチパート メッセージの種類が追加されます。</span><span class="sxs-lookup"><span data-stu-id="208dd-113">The **Multi-part Message Types** folder expands, if collapsed, and a new multi-part message type is added with one default message part.</span></span>  

3.  <span data-ttu-id="208dd-114">マルチパート メッセージの種類、および提供されたメッセージ部分に名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="208dd-114">Name the multi-part message type and the provided message part.</span></span>  

     <span data-ttu-id="208dd-115">名前を割り当てることで他のパーツを追加するには、マルチパート メッセージの種類は、1 つ以上のメッセージ部分を必要とする場合、\<新規\>メッセージ部分。</span><span class="sxs-lookup"><span data-stu-id="208dd-115">If your multi-part message type requires more than one message part, you can add additional parts by assigning a name to the \<New\> message part.</span></span>  

4.  <span data-ttu-id="208dd-116">各メッセージ部分と、.NET クラスまたはスキーマなどの種類を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="208dd-116">Associate each message part with a type, such as a .NET class or schema.</span></span>  

## <a name="remove-a-multi-part-message-type"></a><span data-ttu-id="208dd-117">マルチパート メッセージの種類を削除します。</span><span class="sxs-lookup"><span data-stu-id="208dd-117">Remove a multi-part message type</span></span>  

-   <span data-ttu-id="208dd-118">**オーケストレーション**ウィンドウで、マルチパート メッセージの削除 をクリックする型を右クリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="208dd-118">In the **Orchestration View** window, right-click the multi-part message type you want to remove and then click **Delete**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="208dd-119">オーケストレーションからマルチパート メッセージの種類を削除すると、これが使用されているメッセージからも種類の情報が削除されます。</span><span class="sxs-lookup"><span data-stu-id="208dd-119">Removing a multi-part message type from your orchestration will also remove the type information from messages that use it.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="208dd-120">読み取り専用として表示される項目は、別のオーケストレーションで定義されています。</span><span class="sxs-lookup"><span data-stu-id="208dd-120">Items that appear as read-only are defined in another orchestration.</span></span>  

## <a name="remove-a-part-from-a-multi-part-message-type"></a><span data-ttu-id="208dd-121">マルチパート メッセージの種類からパーツを削除します。</span><span class="sxs-lookup"><span data-stu-id="208dd-121">Remove a part from a multi-part message type</span></span>  

-   <span data-ttu-id="208dd-122">**オーケストレーション**ウィンドウで、削除し、をクリックする部分を右クリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="208dd-122">In the **Orchestration View** window, right-click the part you want to remove and click **Delete**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="208dd-123">場合は、メッセージの種類のメッセージ部分を削除することはできません、**メッセージのボディ部**プロパティが true にします。</span><span class="sxs-lookup"><span data-stu-id="208dd-123">You cannot delete a message type's message part if the **Message Body Part** property is set to true.</span></span> <span data-ttu-id="208dd-124">最初に設定する必要があります、**メッセージのボディ部**プロパティをメッセージの種類の部分の別の True にします。</span><span class="sxs-lookup"><span data-stu-id="208dd-124">You must first set the **Message Body Part** property to True for another of the message type's parts.</span></span>  

## <a name="set-the-type-modifier-for-a-multi-part-message-type"></a><span data-ttu-id="208dd-125">マルチパート メッセージの種類の型修飾子を設定します。</span><span class="sxs-lookup"><span data-stu-id="208dd-125">Set the type modifier for a multi-part message type</span></span>  

- <span data-ttu-id="208dd-126">**プロパティ**ウィンドウで、次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="208dd-126">In the **Properties** window, set the following property:</span></span>  


  |     <span data-ttu-id="208dd-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="208dd-127">Property</span></span>      |                                                                                                                                                                                        <span data-ttu-id="208dd-128">説明</span><span class="sxs-lookup"><span data-stu-id="208dd-128">Description</span></span>                                                                                                                                                                                         |
  |-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
  | <span data-ttu-id="208dd-129">**型修飾子**</span><span class="sxs-lookup"><span data-stu-id="208dd-129">**Type Modifier**</span></span> | <span data-ttu-id="208dd-130">マルチパート メッセージの種類のスコープを設定します。</span><span class="sxs-lookup"><span data-stu-id="208dd-130">Determines the scope of the multi-part message type:</span></span><br /><br /> <span data-ttu-id="208dd-131">-   <strong>Private-</strong>マルチパート メッセージの種類へのアクセスは含まれているモジュールに制限されます。</span><span class="sxs-lookup"><span data-stu-id="208dd-131">-   <strong>Private—</strong>Access to this multi-part message type is limited to the containing module.</span></span><br /><span data-ttu-id="208dd-132">-   <strong>[パブリック]:</strong>マルチパート メッセージの種類へのアクセスは制限されません。</span><span class="sxs-lookup"><span data-stu-id="208dd-132">-   <strong>Public—</strong>Access to this multi-part message type is not limited.</span></span><br /><span data-ttu-id="208dd-133">-   <strong>内部 —</strong>マルチパート メッセージの種類へのアクセスは、同じプロジェクト内のモジュールに制限されます。</span><span class="sxs-lookup"><span data-stu-id="208dd-133">-   <strong>Internal—</strong>Access to this multi-part message type is limited to modules within the same project.</span></span> |

## <a name="add-parts-to-an-existing-multi-part-message"></a><span data-ttu-id="208dd-134">既存のマルチパート メッセージに部分を追加します。</span><span class="sxs-lookup"><span data-stu-id="208dd-134">Add parts to an existing multi-part message</span></span>  

- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="208dd-135">では、マルチパート XLANG メッセージに部分を追加できます。また、最初に宣言した部分の数より大きいインデックスによってメッセージ部分 (存在する場合) を参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="208dd-135">provides the ability to add parts to a multi part XLANG message and also to refer to a message part by an index greater than the originally declared number of parts if the part exists.</span></span> <span data-ttu-id="208dd-136">この機能は、可変数の添付ファイルを含んだ SMTP メッセージを送信または受信する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="208dd-136">This functionality may be useful for sending or receiving SMTP messages with a variable number of attachments.</span></span> <span data-ttu-id="208dd-137">この機能は、次のように実装されます。</span><span class="sxs-lookup"><span data-stu-id="208dd-137">This functionality is implemented as follows:</span></span>  

- <span data-ttu-id="208dd-138">参照を追加、プロジェクトから**Microsoft.XLANGs.BaseTypes**します。</span><span class="sxs-lookup"><span data-stu-id="208dd-138">From your project, add a reference to **Microsoft.XLANGs.BaseTypes**.</span></span>  

- <span data-ttu-id="208dd-139">変数を作成 (たとえば*xlangPart*) 型の**Microsoft.XLANGs.BaseTypes.XLANGMessage**します。</span><span class="sxs-lookup"><span data-stu-id="208dd-139">Create a variable (for example *xlangPart*) of type **Microsoft.XLANGs.BaseTypes.XLANGMessage**.</span></span>  

- <span data-ttu-id="208dd-140">呼び出す<em>xlangPart</em>**します。AddPart(...)** 式図形から適切な引数を使用します。</span><span class="sxs-lookup"><span data-stu-id="208dd-140">Call <em>xlangPart</em>**.AddPart(…)** using the appropriate arguments from an Expression shape.</span></span>  

  > [!NOTE]
  >  <span data-ttu-id="208dd-141">追加された部分は型**XmlDocument**を使用してカスタムの書式設定されたメッセージ部分を追加することはできませんので、 **AddPart()** メソッド。</span><span class="sxs-lookup"><span data-stu-id="208dd-141">The added parts are of type **XmlDocument** so you cannot add a custom formatted message part using the **AddPart()** method.</span></span>  

> [!NOTE]
>  <span data-ttu-id="208dd-142">宣言された部分の数よりも大きい値を含むマルチパート メッセージを受信した場合数の部分がありますが、メッセージでは、オーケストレーション エンジンの読み取りの部分で宣言されたメッセージ部分の数に一致する適切なパートの型を構築します型と、コンストラクト**XmlDocument**パーツの残りの部分。</span><span class="sxs-lookup"><span data-stu-id="208dd-142">If a multi part message that contains greater than the number of declared parts is received, the orchestration engine reads how many parts there are in the message, then constructs the proper part types for the parts that match the number of parts in the declared message type and then constructs **XmlDocument** parts for the remaining parts.</span></span>  

## <a name="see-also"></a><span data-ttu-id="208dd-143">参照</span><span class="sxs-lookup"><span data-stu-id="208dd-143">See Also</span></span>  
 <span data-ttu-id="208dd-144">**IBaseMessage.AddPart メソッド (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="208dd-144">**IBaseMessage.AddPart Method (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>  
 <span data-ttu-id="208dd-145">[Web 上の XSD リソース](../core/xsd-resources-on-the-web.md) </span><span class="sxs-lookup"><span data-stu-id="208dd-145">[XSD Resources on the Web](../core/xsd-resources-on-the-web.md) </span></span>  
 <span data-ttu-id="208dd-146">[識別フィールドとプロパティ フィールドの使用](../core/using-distinguished-fields-and-property-fields.md) </span><span class="sxs-lookup"><span data-stu-id="208dd-146">[Using Distinguished Fields and Property Fields](../core/using-distinguished-fields-and-property-fields.md) </span></span>  
 [<span data-ttu-id="208dd-147">オーケストレーションでのメッセージの使用</span><span class="sxs-lookup"><span data-stu-id="208dd-147">Using Messages in Orchestrations</span></span>](../core/using-messages-in-orchestrations.md)