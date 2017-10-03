---
title: "関連付けの種類を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deleting, correlation types
- correlation types, configuring
- correlation types, deleting
- configuring, correlation types
ms.assetid: cfae4d2e-ec79-45c8-93b3-799dc5e0576e
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 646ac7dafd5207a2558e45252077efe2d9616a70
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-correlation-types"></a><span data-ttu-id="5d245-102">関連付けの種類を構成する方法</span><span class="sxs-lookup"><span data-stu-id="5d245-102">How to Configure Correlation Types</span></span>
<span data-ttu-id="5d245-103">使用する、**関連付けのプロパティ** ダイアログ ボックスを追加または関連付けの種類からプロパティを削除します。</span><span class="sxs-lookup"><span data-stu-id="5d245-103">You use the **Correlation Properties** dialog box to add or remove properties from a correlation type.</span></span> <span data-ttu-id="5d245-104">関連付けの種類は、関連付けセットのプロパティの一覧であり、実行時に送受信の動作によって使用されて、オーケストレーションの正しいインスタンスに受信メッセージが適切に関連付けられるようにします。</span><span class="sxs-lookup"><span data-stu-id="5d245-104">The correlation type lists the properties in a correlation set which are used by Send and Receive activities to make sure that incoming messages are properly correlated with the right instances of an orchestration at run time.</span></span>  
  
 <span data-ttu-id="5d245-105">ダイアログ ボックスにはペインが 2 つあり、それぞれにプロパティの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5d245-105">There are two panes in the dialog box, each containing a list of properties.</span></span> <span data-ttu-id="5d245-106">左ペインの "利用可能なプロパティ" には、プロジェクト内で定義または参照されているプロパティのすべてが、ツリー ビューで表示されます。</span><span class="sxs-lookup"><span data-stu-id="5d245-106">The left pane, "Available Properties", contains a tree view of all of the properties that are defined in your project or referenced by it.</span></span> <span data-ttu-id="5d245-107">既定で表示されるプロパティは、BizTalk Server で定義されているシステム プロパティですが、プロパティ スキーマで独自のプロパティを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="5d245-107">The properties that appear by default are system properties, defined by BizTalk Server, but you can also define your own properties in a property schema.</span></span> <span data-ttu-id="5d245-108">プロパティ スキーマの作成の詳細については、次を参照してください。[プロパティ スキーマ](../core/property-schemas.md)です。</span><span class="sxs-lookup"><span data-stu-id="5d245-108">For more information about creating property schemas, see [Property Schemas](../core/property-schemas.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5d245-109">スキーマのプロパティは、関連付けの種類で使用する前に昇格させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d245-109">Schema properties must be promoted before they can be used in a correlation type.</span></span> <span data-ttu-id="5d245-110">詳細については、次を参照してください。[プロパティの昇格](../core/promoting-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="5d245-110">For more information, see [Promoting Properties](../core/promoting-properties.md).</span></span>  
  
### <a name="to-add-and-configure-a-correlation-type"></a><span data-ttu-id="5d245-111">関連付けの種類を追加および構成するには</span><span class="sxs-lookup"><span data-stu-id="5d245-111">To add and configure a correlation type</span></span>  
  
-   <span data-ttu-id="5d245-112">オーケストレーションの種類 ウィンドウで、右クリック**関連付けの種類** をクリックし、**新しい関連付けの種類**です。</span><span class="sxs-lookup"><span data-stu-id="5d245-112">In the Orchestration View window, right-click **Correlation Types** and then click **New Correlation Type**.</span></span>  
  
     <span data-ttu-id="5d245-113">**関連付けのプロパティ** ダイアログ ボックスが表示されたらです。</span><span class="sxs-lookup"><span data-stu-id="5d245-113">The **Correlation Properties** dialog box comes up.</span></span> <span data-ttu-id="5d245-114">関連付けの種類に含めるプロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="5d245-114">Add properties that you want to include in your correlation type.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5d245-115">アクセスする場合、**関連付けのプロパティ** ダイアログ ボックスを直接相関関係の設定が既に存在しない場合、関連付けセットの関連付けの種類が作成されます。</span><span class="sxs-lookup"><span data-stu-id="5d245-115">If you access the **Correlation Properties** dialog box directly from a correlation set, a correlation type for the correlation set is created if one does not already exist.</span></span> <span data-ttu-id="5d245-116">加えた変更は、新しい関連付けの種類に保存され、関連付けセットは、新しい関連付けの種類を使用するよう構成されます。</span><span class="sxs-lookup"><span data-stu-id="5d245-116">Your changes will be saved to the new correlation type, and the correlation set will be configured to use the new correlation type.</span></span> <span data-ttu-id="5d245-117">関連付けセットに関連付けの種類が既にあった場合、変更を加えると、その関連付けの種類が変更されます。</span><span class="sxs-lookup"><span data-stu-id="5d245-117">If a correlation type already existed for the correlation set and you make changes, the correlation type will be modified.</span></span>  
  
### <a name="to-remove-a-correlation-type"></a><span data-ttu-id="5d245-118">関連付けの種類を削除するには</span><span class="sxs-lookup"><span data-stu-id="5d245-118">To remove a correlation type</span></span>  
  
-   <span data-ttu-id="5d245-119">オーケストレーションの種類 ウィンドウで、をクリックして削除する関連付けの種類を右クリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="5d245-119">In the Orchestration View window, right-click the correlation type you want to remove and then click **Delete**.</span></span>