---
title: インターフェイスをセキュリティで保護されたコンポーネントを支援する方法 |Microsoft Docs
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
ms.openlocfilehash: 9ca6e0dcbd265dbfcdc6f128f2ff7b58e301f2e6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385027"
---
# <a name="how-to-help-secure-component-interfaces"></a><span data-ttu-id="a76b5-102">コンポーネント インターフェイスをセキュリティ保護する方法</span><span class="sxs-lookup"><span data-stu-id="a76b5-102">How to Help Secure Component Interfaces</span></span>
<span data-ttu-id="a76b5-103">コンポーネント インターフェイスのテストを開始する前に、そのセキュリティを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a76b5-103">Before you can start testing a component interface, you must set up security for it.</span></span> <span data-ttu-id="a76b5-104">次の手順は、PeopleSoft バージョン 8.4 のコンポーネント インターフェイスのセキュリティを構成する方法をについて説明しますが、バージョン 8.1 の手順を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="a76b5-104">The following procedure describes how to configure component interface security for PeopleSoft Version 8.4, but you can use the procedure for Version 8.1.</span></span>  
  
### <a name="to-configure-interface-security"></a><span data-ttu-id="a76b5-105">インターフェイスのセキュリティを構成するには</span><span class="sxs-lookup"><span data-stu-id="a76b5-105">To configure interface security</span></span>  
  
1.  <span data-ttu-id="a76b5-106">展開**PeopleTools**、展開**セキュリティ**、展開**ユーザー プロファイル**、順に展開**アクセス許可とロール**します。</span><span class="sxs-lookup"><span data-stu-id="a76b5-106">Expand **PeopleTools**, expand **Security**, expand **User Profiles**, and then expand **Permissions & Roles**.</span></span>  
  
     <span data-ttu-id="a76b5-107">![](../core/media/psadapter-47-ps-configsecurity1.gif "PSAdapter_47_PS_ConfigSecurity1")</span><span class="sxs-lookup"><span data-stu-id="a76b5-107">![](../core/media/psadapter-47-ps-configsecurity1.gif "PSAdapter_47_PS_ConfigSecurity1")</span></span>  
  
2.  <span data-ttu-id="a76b5-108">クリックして**アクセス許可の一覧**します。</span><span class="sxs-lookup"><span data-stu-id="a76b5-108">Click **Permission Lists**.</span></span>  
  
3.  <span data-ttu-id="a76b5-109">**[検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a76b5-109">Click **Search**.</span></span>  
  
     <span data-ttu-id="a76b5-110">![](../core/media/psadapter-48-ps-configsecurity2.gif "PSAdapter_48_PS_ConfigSecurity2")</span><span class="sxs-lookup"><span data-stu-id="a76b5-110">![](../core/media/psadapter-48-ps-configsecurity2.gif "PSAdapter_48_PS_ConfigSecurity2")</span></span>  
  
4.  <span data-ttu-id="a76b5-111">**Permission Lists Search**ウィンドウで、関連するアクセス許可の一覧を選択します。</span><span class="sxs-lookup"><span data-stu-id="a76b5-111">In the **Permission Lists Search** pane, select the relevant permission list.</span></span>  
  
     <span data-ttu-id="a76b5-112">次のウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a76b5-112">The following window appears.</span></span>  
  
     <span data-ttu-id="a76b5-113">![](../core/media/psadapter-49-ps-configsecurity3.gif "PSAdapter_49_PS_ConfigSecurity3")</span><span class="sxs-lookup"><span data-stu-id="a76b5-113">![](../core/media/psadapter-49-ps-configsecurity3.gif "PSAdapter_49_PS_ConfigSecurity3")</span></span>  
  
5.  <span data-ttu-id="a76b5-114">右矢印をクリックして、 **sign-on Times**タブを複数のタブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a76b5-114">Click the right arrow next to the **Sign-on Times** tab to display more tabs.</span></span>  
  
     <span data-ttu-id="a76b5-115">![](../core/media/psadapter-50-ps-configsecurity4.gif "PSAdapter_50_PS_ConfigSecurity4")</span><span class="sxs-lookup"><span data-stu-id="a76b5-115">![](../core/media/psadapter-50-ps-configsecurity4.gif "PSAdapter_50_PS_ConfigSecurity4")</span></span>  
  
6.  <span data-ttu-id="a76b5-116">をクリックして、**コンポーネント インターフェイス**タブ。</span><span class="sxs-lookup"><span data-stu-id="a76b5-116">Click the **Component Interfaces** tab.</span></span>  
  
7.  <span data-ttu-id="a76b5-117">をクリックして、+ (プラス) 記号を新しい行を追加、**コンポーネント インターフェイス**一覧。</span><span class="sxs-lookup"><span data-stu-id="a76b5-117">Click the + (plus) sign to add a new row to the **Component Interfaces** list.</span></span>  
  
     <span data-ttu-id="a76b5-118">コンポーネント インターフェイスの名前を入力できるフィールドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a76b5-118">A field appears in which you can type the component interface name.</span></span>  
  
     <span data-ttu-id="a76b5-119">![](../core/media/psadapter-51-ps-configsecurity5.gif "PSAdapter_51_PS_ConfigSecurity5")</span><span class="sxs-lookup"><span data-stu-id="a76b5-119">![](../core/media/psadapter-51-ps-configsecurity5.gif "PSAdapter_51_PS_ConfigSecurity5")</span></span>  
  
8.  <span data-ttu-id="a76b5-120">コンポーネント インターフェイスの名前を入力し、クリックして**編集**します。</span><span class="sxs-lookup"><span data-stu-id="a76b5-120">Type the component interface name, and then click **Edit**.</span></span>  
  
     <span data-ttu-id="a76b5-121">この例では、AR_ITEM_AGENT のコンポーネント インターフェイスを使用します。</span><span class="sxs-lookup"><span data-stu-id="a76b5-121">This example uses component interface AR_ITEM_AGENT.</span></span>  
  
     <span data-ttu-id="a76b5-122">![](../core/media/psadapter-52-ps-configsecurity6.gif "PSAdapter_52_PS_ConfigSecurity6")</span><span class="sxs-lookup"><span data-stu-id="a76b5-122">![](../core/media/psadapter-52-ps-configsecurity6.gif "PSAdapter_52_PS_ConfigSecurity6")</span></span>  
  
9. <span data-ttu-id="a76b5-123">一覧で、各メソッドでは、必要なアクセス レベルを選択し、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="a76b5-123">In the list, select the desired access level for each method, and then click **OK**.</span></span>  
  
     <span data-ttu-id="a76b5-124">次のウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a76b5-124">The following window appears.</span></span>  
  
     <span data-ttu-id="a76b5-125">![](../core/media/psadapter-53-ps-configsecurity7.gif "PSAdapter_53_PS_ConfigSecurity7")</span><span class="sxs-lookup"><span data-stu-id="a76b5-125">![](../core/media/psadapter-53-ps-configsecurity7.gif "PSAdapter_53_PS_ConfigSecurity7")</span></span>  
  
10. <span data-ttu-id="a76b5-126">右側のウィンドウで下にスクロールし、をクリックして**保存**します。</span><span class="sxs-lookup"><span data-stu-id="a76b5-126">Scroll down in the right pane, and click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a76b5-127">参照</span><span class="sxs-lookup"><span data-stu-id="a76b5-127">See Also</span></span>  
 <span data-ttu-id="a76b5-128">[付録 a:コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md) </span><span class="sxs-lookup"><span data-stu-id="a76b5-128">[Appendix A: Component Interface Methods](../core/appendix-a-component-interface-methods.md) </span></span>  
 [<span data-ttu-id="a76b5-129">付録 c:コンポーネント インターフェイスの使用</span><span class="sxs-lookup"><span data-stu-id="a76b5-129">Appendix C: Using Component Interfaces</span></span>](../core/appendix-c-using-component-interfaces.md)