---
title: インターフェイスをセキュリティで保護されたコンポーネントを保護する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- component interfaces, helping to secure
- security, component interfaces
ms.assetid: 03b2af44-78e7-4fdc-bfa3-7697b2a60986
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54136aaeae9578ae4e438c5bd8b95b902d618f96
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255218"
---
# <a name="how-to-help-secure-component-interfaces"></a><span data-ttu-id="0ebe1-102">コンポーネント インターフェイスをセキュリティで保護する方法</span><span class="sxs-lookup"><span data-stu-id="0ebe1-102">How to Help Secure Component Interfaces</span></span>
<span data-ttu-id="0ebe1-103">コンポーネント インターフェイスのテストを開始する前に、セキュリティを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ebe1-103">Before you can start testing a component interface, you must set up security for it.</span></span> <span data-ttu-id="0ebe1-104">次の手順では、PeopleSoft バージョン 8.4 のコンポーネント インターフェイスのセキュリティを構成する方法について説明しますが、この手順はバージョン 8.1 にも使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ebe1-104">The following procedure describes how to configure component interface security for PeopleSoft Version 8.4, but you can use the procedure for Version 8.1.</span></span>  
  
### <a name="to-configure-interface-security"></a><span data-ttu-id="0ebe1-105">インターフェイスのセキュリティを構成するには</span><span class="sxs-lookup"><span data-stu-id="0ebe1-105">To configure interface security</span></span>  
  
1.  <span data-ttu-id="0ebe1-106">展開**PeopleTools**、展開**セキュリティ**、展開**ユーザー プロファイル**、順に展開**アクセス許可とロール**です。</span><span class="sxs-lookup"><span data-stu-id="0ebe1-106">Expand **PeopleTools**, expand **Security**, expand **User Profiles**, and then expand **Permissions & Roles**.</span></span>  
  
     ![](../core/media/psadapter-47-ps-configsecurity1.gif "PSAdapter_47_PS_ConfigSecurity1")  
  
2.  <span data-ttu-id="0ebe1-107">をクリックして**アクセス許可の一覧**です。</span><span class="sxs-lookup"><span data-stu-id="0ebe1-107">Click **Permission Lists**.</span></span>  
  
3.  <span data-ttu-id="0ebe1-108">**[検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0ebe1-108">Click **Search**.</span></span>  
  
     ![](../core/media/psadapter-48-ps-configsecurity2.gif "PSAdapter_48_PS_ConfigSecurity2")  
  
4.  <span data-ttu-id="0ebe1-109">**Permission Lists Search**  ウィンドウで、関連するアクセス許可リストを選択します。</span><span class="sxs-lookup"><span data-stu-id="0ebe1-109">In the **Permission Lists Search** pane, select the relevant permission list.</span></span>  
  
     <span data-ttu-id="0ebe1-110">次のようなウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ebe1-110">The following window appears.</span></span>  
  
     ![](../core/media/psadapter-49-ps-configsecurity3.gif "PSAdapter_49_PS_ConfigSecurity3")  
  
5.  <span data-ttu-id="0ebe1-111">次に、右矢印をクリックして、 **sign-on Times**他のタブを表示するタブです。</span><span class="sxs-lookup"><span data-stu-id="0ebe1-111">Click the right arrow next to the **Sign-on Times** tab to display more tabs.</span></span>  
  
     ![](../core/media/psadapter-50-ps-configsecurity4.gif "PSAdapter_50_PS_ConfigSecurity4")  
  
6.  <span data-ttu-id="0ebe1-112">クリックして、**コンポーネント インターフェイス**タブです。</span><span class="sxs-lookup"><span data-stu-id="0ebe1-112">Click the **Component Interfaces** tab.</span></span>  
  
7.  <span data-ttu-id="0ebe1-113">クリックして、+ (に新しい行を追加する記号 +)、**コンポーネント インターフェイス** ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="0ebe1-113">Click the + (plus) sign to add a new row to the **Component Interfaces** list.</span></span>  
  
     <span data-ttu-id="0ebe1-114">コンポーネント インターフェイス名を入力できるフィールドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ebe1-114">A field appears in which you can type the component interface name.</span></span>  
  
     ![](../core/media/psadapter-51-ps-configsecurity5.gif "PSAdapter_51_PS_ConfigSecurity5")  
  
8.  <span data-ttu-id="0ebe1-115">コンポーネント インターフェイスの名前を入力して、クリックして**編集**です。</span><span class="sxs-lookup"><span data-stu-id="0ebe1-115">Type the component interface name, and then click **Edit**.</span></span>  
  
     <span data-ttu-id="0ebe1-116">この例では、AR_ITEM_AGENT というコンポーネント インターフェイスを使用しています。</span><span class="sxs-lookup"><span data-stu-id="0ebe1-116">This example uses component interface AR_ITEM_AGENT.</span></span>  
  
     ![](../core/media/psadapter-52-ps-configsecurity6.gif "PSAdapter_52_PS_ConfigSecurity6")  
  
9. <span data-ttu-id="0ebe1-117">一覧で、各メソッドで必要なアクセス レベルを選択し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="0ebe1-117">In the list, select the desired access level for each method, and then click **OK**.</span></span>  
  
     <span data-ttu-id="0ebe1-118">次のようなウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ebe1-118">The following window appears.</span></span>  
  
     ![](../core/media/psadapter-53-ps-configsecurity7.gif "PSAdapter_53_PS_ConfigSecurity7")  
  
10. <span data-ttu-id="0ebe1-119">右側のペインで下にスクロールし、をクリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="0ebe1-119">Scroll down in the right pane, and click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ebe1-120">参照</span><span class="sxs-lookup"><span data-stu-id="0ebe1-120">See Also</span></span>  
 <span data-ttu-id="0ebe1-121">[付録 a: コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md) </span><span class="sxs-lookup"><span data-stu-id="0ebe1-121">[Appendix A: Component Interface Methods](../core/appendix-a-component-interface-methods.md) </span></span>  
 [<span data-ttu-id="0ebe1-122">付録 c: コンポーネント インターフェイスの使用</span><span class="sxs-lookup"><span data-stu-id="0ebe1-122">Appendix C: Using Component Interfaces</span></span>](../core/appendix-c-using-component-interfaces.md)