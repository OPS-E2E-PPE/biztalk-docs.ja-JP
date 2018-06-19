---
title: オプションの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3f4b0b51-2cad-4cb5-b6cd-4db92bd199fa
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b19646c9c83eff4a3171b4d25763a6b581d45b1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976760"
---
# <a name="optional-configurations"></a><span data-ttu-id="44670-102">オプションの構成</span><span class="sxs-lookup"><span data-stu-id="44670-102">Optional Configurations</span></span>
<span data-ttu-id="44670-103">BizTalk Server 管理パックをインポートした後、[監視] ウィンドウのナビゲーション ウィンドウには、自動的に検出されるオブジェクトの種類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="44670-103">After you import the BizTalk Server Management Pack, the navigation pane of the Monitoring pane displays the object types that are discovered automatically.</span></span> <span data-ttu-id="44670-104">オブジェクトの種類の一覧は、次を参照してください。[管理パックで検出されるオブジェクト](../technical-guides/objects-the-management-pack-discovers.md)セクションです。</span><span class="sxs-lookup"><span data-stu-id="44670-104">For a list of object types, see [Objects the Management Pack Discovers](../technical-guides/objects-the-management-pack-discovers.md) section.</span></span> <span data-ttu-id="44670-105">によって検出されるオブジェクトの既定の検出構成を変更することができます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パック。</span><span class="sxs-lookup"><span data-stu-id="44670-105">You can modify the default discovery configuration of objects discovered by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management Pack.</span></span> <span data-ttu-id="44670-106">構成設定を変更するのにには、Operations Manager 2007 R2 または 2012 の上書き機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="44670-106">You use the overrides feature of Operations Manager 2007 R2/2012 to change configuration settings.</span></span>  
  
 <span data-ttu-id="44670-107">自動的に検出されていないオブジェクトの種類の自動検出の設定を有効にできます、 **Authoring**オペレーション コンソール ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="44670-107">For an object type that is not automatically discovered, you can enable setting for automatic discovery in the **Authoring** pane in the Operations Console.</span></span>  
  
#### <a name="to-use-an-override-to-change-the-setting-for-automatic-discovery"></a><span data-ttu-id="44670-108">上書きを使用して自動検出の設定を変更するには</span><span class="sxs-lookup"><span data-stu-id="44670-108">To use an override to change the setting for automatic discovery</span></span>  
  
1.  <span data-ttu-id="44670-109">作成 ウィンドウで **管理パック オブジェクト**、順にクリック**オブジェクト検出**です。</span><span class="sxs-lookup"><span data-stu-id="44670-109">In the Authoring pane, expand **Management Pack Objects**, and then click **Object Discoveries**.</span></span>  
  
2.  <span data-ttu-id="44670-110">Operations Manager ツールバーで、をクリックして**スコープ**、および BizTalk Server のオブジェクトのみを含めるには、詳細ウィンドウに表示されているオブジェクトをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="44670-110">On the Operations Manager toolbar, click **Scope**, and filter the objects that appear in the details pane to include only BizTalk Server objects.</span></span>  
  
3.  <span data-ttu-id="44670-111">詳細ウィンドウでの設定を変更するオブジェクトの種類をクリックします。</span><span class="sxs-lookup"><span data-stu-id="44670-111">In the details pane, click the object type you want to change the setting for.</span></span>  
  
4.  <span data-ttu-id="44670-112">Operations Manager ツールバーで、をクリックして**オーバーライド**をクリックして**オブジェクト検出の上書き**、いずれかをクリックして**型のすべてのオブジェクト:** \< *オブジェクトの種類の名前*\>、**グループの特定のオブジェクト型の場合:** \<*オブジェクトの種類の名前*\>、または**別の型のすべてのオブジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="44670-112">On the Operations Manager toolbar, click **Overrides**, click **Override the Object Discovery**, and then click either **For all objects of type:** \<*name of object type*\>, **For a group, For a specific object of type:** \<*name of object type*\>, or **For all objects of another type**.</span></span>  
  
5.  <span data-ttu-id="44670-113">**上書きのプロパティ**ダイアログ ボックスで、をクリックして、**オーバーライド**のボックス、**有効**パラメーターを変更します。</span><span class="sxs-lookup"><span data-stu-id="44670-113">In the **Override Properties** dialog box, click the **Override** box for the **Enabled** parameter you want to change.</span></span>  
  
6.  <span data-ttu-id="44670-114">[**管理パック**、] をクリックして**新規**管理パックの封印されていないバージョンを作成し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="44670-114">Under **Management Pack**, click **New** to create an unsealed version of the Management Pack, and then click **OK**.</span></span>  
  
 <span data-ttu-id="44670-115">上書きの設定を変更すると、オブジェクトの種類が自動的に検出し、[監視] ウィンドウで表示されます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="44670-115">After you change the override setting, the object type will be automatically discovered and will appear in the Monitoring pane under [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="44670-116">設定の上書きについては、次を参照してください。 [Operations Manager 2007 R2 または 2012 よりも優先](http://go.microsoft.com/fwlink/?LinkId=86870)(http://go.microsoft.com/fwlink/?LinkId=86870)。</span><span class="sxs-lookup"><span data-stu-id="44670-116">For information about setting overrides, see [Overrides in Operations Manager 2007 R2/2012](http://go.microsoft.com/fwlink/?LinkId=86870) (http://go.microsoft.com/fwlink/?LinkId=86870).</span></span>