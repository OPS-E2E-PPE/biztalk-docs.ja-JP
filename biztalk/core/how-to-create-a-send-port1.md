---
title: "送信 Port1 を作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating send ports
- send ports, creating
ms.assetid: bf32e9f5-ebed-43d2-b9a9-6ab91925d973
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61c82b199f7b8686556f2cbb53a90b0d4b59536e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-send-port"></a><span data-ttu-id="02517-102">送信ポートを作成する方法</span><span class="sxs-lookup"><span data-stu-id="02517-102">How to Create a Send Port</span></span>
<span data-ttu-id="02517-103">JD Edwards EnterpriseOne 用の BizTalk Server 送信ポートを作成するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="02517-103">Use the following procedure to create BizTalk Server send ports for JD Edwards EnterpriseOne.</span></span>  
  
### <a name="to-create-a-send-port"></a><span data-ttu-id="02517-104">送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="02517-104">To create a send port</span></span>  
  
1.  <span data-ttu-id="02517-105">[送信ポート] ノードを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="02517-105">Right-click the Send Ports node.</span></span>  
  
2.  <span data-ttu-id="02517-106">をクリックして**送信ポートの追加**です。</span><span class="sxs-lookup"><span data-stu-id="02517-106">Click **Add Send Port**.</span></span>  
  
3.  <span data-ttu-id="02517-107">**新しい送信ポートを作成**ダイアログ ボックスで、**静的な送信請求-応答ポート**から、**送信ポートの種類の指定**ボックスの一覧し、をクリックして**OK**.</span><span class="sxs-lookup"><span data-stu-id="02517-107">In the **Create New Send Port** dialog box, select **Static Solicit-Response Port** from the **Specify the type of Send Port** list, and click **OK**.</span></span>  
  
     <span data-ttu-id="02517-108">**静的な送信請求-応答送信ポート プロパティ**ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="02517-108">The **Static Solicit-Response Send Port Properties** window opens.</span></span>  
  
4.  <span data-ttu-id="02517-109">たとえば、送信ポートの名前を入力`SSOSendToJDEEntOne`です。</span><span class="sxs-lookup"><span data-stu-id="02517-109">Type a name for the send port, for example, `SSOSendToJDEEntOne`.</span></span>  
  
5.  <span data-ttu-id="02517-110">をクリックして**トランスポート**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="02517-110">Click **Transport** in the left pane.</span></span>  
  
6.  <span data-ttu-id="02517-111">をクリックして**トランスポートの種類**を選択して**[jdeentone]**です。</span><span class="sxs-lookup"><span data-stu-id="02517-111">Click **Transport Type**, and select **JDEEntOne**.</span></span>  
  
7.  <span data-ttu-id="02517-112">選択、**アドレス (URI)**、省略記号 (...) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="02517-112">Select the **Address (URI)**, and click the ellipsis (…) button.</span></span>  
  
     <span data-ttu-id="02517-113">JD Edwards EnterpriseOne**トランスポートのプロパティ** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="02517-113">The JD Edwards EnterpriseOne **Transport Properties** dialog box appears.</span></span>  
  
8.  <span data-ttu-id="02517-114">型`myJDEEntOneSSO`の**論理システム名**です。</span><span class="sxs-lookup"><span data-stu-id="02517-114">Type `myJDEEntOneSSO` for the **Logical System Name**.</span></span>  
  
9. <span data-ttu-id="02517-115">選択**はい**の**SSO を使用して**です。</span><span class="sxs-lookup"><span data-stu-id="02517-115">Select **Yes** for **Use SSO**.</span></span>  
  
10. <span data-ttu-id="02517-116">一覧で、JD Edwards EnterpriseOne システムを表すよう作成したシングル サインオン (SSO) 関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="02517-116">In the drop-down list, select the Single Sign-On (SSO) affiliate application that you created to represent the JD Edwards EnterpriseOne system.</span></span>  
  
     <span data-ttu-id="02517-117">をクリックして**OK**入力した情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="02517-117">Click **OK** to confirm the information you entered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02517-118">参照</span><span class="sxs-lookup"><span data-stu-id="02517-118">See Also</span></span>  
 <span data-ttu-id="02517-119">[関連アプリケーションの作成](../core/creating-affiliate-applications4.md) </span><span class="sxs-lookup"><span data-stu-id="02517-119">[Creating Affiliate Applications](../core/creating-affiliate-applications4.md) </span></span>  
 [<span data-ttu-id="02517-120">シングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="02517-120">Using Single Sign-On</span></span>](../core/using-single-sign-on1.md)