---
title: 関連付けの種類を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, correlation types
- correlation types, configuring
- correlation types, deleting
- configuring, correlation types
ms.assetid: cfae4d2e-ec79-45c8-93b3-799dc5e0576e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69770055b1d373b355bfd853e26bf463aab1858d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341494"
---
# <a name="how-to-configure-correlation-types"></a><span data-ttu-id="adcc6-102">関連付けの種類を構成する方法</span><span class="sxs-lookup"><span data-stu-id="adcc6-102">How to Configure Correlation Types</span></span>
<span data-ttu-id="adcc6-103">使用する、**関連付けのプロパティ** ダイアログ ボックスを追加または関連付けの種類からのプロパティを削除します。</span><span class="sxs-lookup"><span data-stu-id="adcc6-103">You use the **Correlation Properties** dialog box to add or remove properties from a correlation type.</span></span> <span data-ttu-id="adcc6-104">関連付けの種類には、送信でが使用され、実行時にオーケストレーションの適切なインスタンスで、受信メッセージが正しく関連付けられないことを確認するアクティビティを受信する、関連付けセットのプロパティが一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="adcc6-104">The correlation type lists the properties in a correlation set which are used by Send and Receive activities to make sure that incoming messages are properly correlated with the right instances of an orchestration at run time.</span></span>  
  
 <span data-ttu-id="adcc6-105">プロパティの一覧を格納している各ダイアログ ボックスには、2 つのペインがあります。</span><span class="sxs-lookup"><span data-stu-id="adcc6-105">There are two panes in the dialog box, each containing a list of properties.</span></span> <span data-ttu-id="adcc6-106">左側のウィンドウでは、「使用可能なプロパティ」には、すべてのプロパティは、プロジェクトで定義されているまたはその参照先のツリー ビューが含まれています。</span><span class="sxs-lookup"><span data-stu-id="adcc6-106">The left pane, "Available Properties", contains a tree view of all of the properties that are defined in your project or referenced by it.</span></span> <span data-ttu-id="adcc6-107">既定で表示されるプロパティは、BizTalk Server で定義されている、システム プロパティがプロパティ スキーマで、独自のプロパティを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="adcc6-107">The properties that appear by default are system properties, defined by BizTalk Server, but you can also define your own properties in a property schema.</span></span> <span data-ttu-id="adcc6-108">プロパティ スキーマの作成の詳細については、次を参照してください。[プロパティ スキーマ](../core/property-schemas.md)します。</span><span class="sxs-lookup"><span data-stu-id="adcc6-108">For more information about creating property schemas, see [Property Schemas](../core/property-schemas.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="adcc6-109">関連付けの種類で使用するに、スキーマのプロパティを昇格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="adcc6-109">Schema properties must be promoted before they can be used in a correlation type.</span></span> <span data-ttu-id="adcc6-110">詳細については、次を参照してください。[プロパティの昇格](../core/promoting-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="adcc6-110">For more information, see [Promoting Properties](../core/promoting-properties.md).</span></span>  
  
### <a name="to-add-and-configure-a-correlation-type"></a><span data-ttu-id="adcc6-111">追加して、関連付けの種類を構成するには</span><span class="sxs-lookup"><span data-stu-id="adcc6-111">To add and configure a correlation type</span></span>  
  
-   <span data-ttu-id="adcc6-112">オーケストレーションの種類 ウィンドウで、右クリック**関連付けの種類**し**新しい関連付けの種類**します。</span><span class="sxs-lookup"><span data-stu-id="adcc6-112">In the Orchestration View window, right-click **Correlation Types** and then click **New Correlation Type**.</span></span>  
  
     <span data-ttu-id="adcc6-113">**関連付けのプロパティ** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="adcc6-113">The **Correlation Properties** dialog box comes up.</span></span> <span data-ttu-id="adcc6-114">関連付けの種類で追加するプロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="adcc6-114">Add properties that you want to include in your correlation type.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="adcc6-115">アクセスする場合、**関連付けのプロパティ**ダイアログ ボックスで直接関連付けセットが既に存在しない場合、関連付けセットの関連付けの種類が作成されます。</span><span class="sxs-lookup"><span data-stu-id="adcc6-115">If you access the **Correlation Properties** dialog box directly from a correlation set, a correlation type for the correlation set is created if one does not already exist.</span></span> <span data-ttu-id="adcc6-116">新しい関連付けの種類に変更が保存され、関連付けセットは、新しい関連付けの種類を使用するように構成されます。</span><span class="sxs-lookup"><span data-stu-id="adcc6-116">Your changes will be saved to the new correlation type, and the correlation set will be configured to use the new correlation type.</span></span> <span data-ttu-id="adcc6-117">関連付けセットの関連付けの種類が既に存在して、変更を加えた場合は、関連付けの種類が変更されます。</span><span class="sxs-lookup"><span data-stu-id="adcc6-117">If a correlation type already existed for the correlation set and you make changes, the correlation type will be modified.</span></span>  
  
### <a name="to-remove-a-correlation-type"></a><span data-ttu-id="adcc6-118">関連付けの種類を削除するには</span><span class="sxs-lookup"><span data-stu-id="adcc6-118">To remove a correlation type</span></span>  
  
-   <span data-ttu-id="adcc6-119">オーケストレーションの種類 ウィンドウで、クリックして削除する関連付けの種類を右クリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="adcc6-119">In the Orchestration View window, right-click the correlation type you want to remove and then click **Delete**.</span></span>