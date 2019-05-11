---
title: 送信 Port1 を作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating send ports
- send ports, creating
ms.assetid: bf32e9f5-ebed-43d2-b9a9-6ab91925d973
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a0657f32edfbddd3830605d271daafc632db60d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385563"
---
# <a name="how-to-create-a-send-port"></a><span data-ttu-id="6b089-102">送信ポートを作成する方法</span><span class="sxs-lookup"><span data-stu-id="6b089-102">How to Create a Send Port</span></span>
<span data-ttu-id="6b089-103">JD Edwards EnterpriseOne の送信ポートを BizTalk Server を作成する次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="6b089-103">Use the following procedure to create BizTalk Server send ports for JD Edwards EnterpriseOne.</span></span>  
  
### <a name="to-create-a-send-port"></a><span data-ttu-id="6b089-104">送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="6b089-104">To create a send port</span></span>  
  
1.  <span data-ttu-id="6b089-105">送信ポート ノードを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="6b089-105">Right-click the Send Ports node.</span></span>  
  
2.  <span data-ttu-id="6b089-106">クリックして**送信ポートの追加**します。</span><span class="sxs-lookup"><span data-stu-id="6b089-106">Click **Add Send Port**.</span></span>  
  
3.  <span data-ttu-id="6b089-107">**新しい送信ポートを作成**ダイアログ ボックスで、**静的な送信請求-応答ポート**から、**送信ポートの種類を指定**ボックスの一覧し、をクリックして**OK**.</span><span class="sxs-lookup"><span data-stu-id="6b089-107">In the **Create New Send Port** dialog box, select **Static Solicit-Response Port** from the **Specify the type of Send Port** list, and click **OK**.</span></span>  
  
     <span data-ttu-id="6b089-108">**静的な送信請求-応答送信ポートのプロパティ**ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="6b089-108">The **Static Solicit-Response Send Port Properties** window opens.</span></span>  
  
4.  <span data-ttu-id="6b089-109">たとえば、送信ポートの名前を入力`SSOSendToJDEEntOne`します。</span><span class="sxs-lookup"><span data-stu-id="6b089-109">Type a name for the send port, for example, `SSOSendToJDEEntOne`.</span></span>  
  
5.  <span data-ttu-id="6b089-110">クリックして**トランスポート**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="6b089-110">Click **Transport** in the left pane.</span></span>  
  
6.  <span data-ttu-id="6b089-111">クリックして**トランスポートの種類**、選択および **[jdeentone]** します。</span><span class="sxs-lookup"><span data-stu-id="6b089-111">Click **Transport Type**, and select **JDEEntOne**.</span></span>  
  
7.  <span data-ttu-id="6b089-112">選択、**アドレス (URI)**、省略記号 (...) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b089-112">Select the **Address (URI)**, and click the ellipsis (…) button.</span></span>  
  
     <span data-ttu-id="6b089-113">JD Edwards EnterpriseOne**トランスポートのプロパティ** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b089-113">The JD Edwards EnterpriseOne **Transport Properties** dialog box appears.</span></span>  
  
8.  <span data-ttu-id="6b089-114">型`myJDEEntOneSSO`の**論理システム名**します。</span><span class="sxs-lookup"><span data-stu-id="6b089-114">Type `myJDEEntOneSSO` for the **Logical System Name**.</span></span>  
  
9. <span data-ttu-id="6b089-115">選択**はい**の**SSO を使用して、** します。</span><span class="sxs-lookup"><span data-stu-id="6b089-115">Select **Yes** for **Use SSO**.</span></span>  
  
10. <span data-ttu-id="6b089-116">ボックスの一覧では、JD Edwards EnterpriseOne システムを表すよう作成したシングル サインオン (SSO) 関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="6b089-116">In the drop-down list, select the Single Sign-On (SSO) affiliate application that you created to represent the JD Edwards EnterpriseOne system.</span></span>  
  
     <span data-ttu-id="6b089-117">クリックして**OK**を入力した情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="6b089-117">Click **OK** to confirm the information you entered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b089-118">参照</span><span class="sxs-lookup"><span data-stu-id="6b089-118">See Also</span></span>  
 <span data-ttu-id="6b089-119">[関連アプリケーションの作成](../core/creating-affiliate-applications4.md) </span><span class="sxs-lookup"><span data-stu-id="6b089-119">[Creating Affiliate Applications](../core/creating-affiliate-applications4.md) </span></span>  
 [<span data-ttu-id="6b089-120">BizTalk Adapter for JD Edwards EnterpriseOne のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="6b089-120">Security in BizTalk Adapter for JD Edwards EnterpriseOne</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)