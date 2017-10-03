---
title: "HTTP 受信 Adapter2 を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP receive adapter, configuring
- configuring HTTP receive adapter
ms.assetid: dd26fd57-90d8-4ffe-b56f-8de55ecc6f68
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c39e55ca233ef9875d3d56d25312ef879e3c539
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-http-receive-adapter"></a><span data-ttu-id="0f130-102">HTTP 受信アダプターを構成する方法</span><span class="sxs-lookup"><span data-stu-id="0f130-102">How to Configure the HTTP Receive Adapter</span></span>
<span data-ttu-id="0f130-103">HTTP 受信アダプターを使用すると、メッセージを BizTalk Server に送信できます。</span><span class="sxs-lookup"><span data-stu-id="0f130-103">You can use the HTTP receive adapter to submit messages to BizTalk Server.</span></span> <span data-ttu-id="0f130-104">HTTP 受信アダプターは、インターネット インフォメーション サービス (IIS) プロセスでホストされる IIS の ISAPI 拡張です。</span><span class="sxs-lookup"><span data-stu-id="0f130-104">The HTTP receive adapter is an Internet Information Services (IIS) ISAPI extension that is hosted in the IIS process.</span></span>  
  
### <a name="to-configure-the-http-receive-adapter"></a><span data-ttu-id="0f130-105">HTTP 受信アダプターを構成するには</span><span class="sxs-lookup"><span data-stu-id="0f130-105">To configure the HTTP receive adapter</span></span>  
  
1.  <span data-ttu-id="0f130-106">HTTP 受信アダプター (BTSHTTPReceive.dll) から **\<BizTalk2010 > \HttpReceive >**シングル サインオン (SSO) プロジェクトを含むフォルダーに (たとえば、 **< Adapter_install > \biztalk2010\SSO\mySSODemo**)。</span><span class="sxs-lookup"><span data-stu-id="0f130-106">Copy the HTTP receive adapter (BTSHTTPReceive.dll) from **\<BizTalk2010>\HttpReceive>** to the folder containing your Single Sign-On (SSO) project (for example, **<Adapter_install>\biztalk2010\SSO\mySSODemo**).</span></span>  
  
    1.  <span data-ttu-id="0f130-107">新しい Web サービス拡張機能 mySSODemo を追加します。</span><span class="sxs-lookup"><span data-stu-id="0f130-107">Add a new Web service extension mySSODemo.</span></span>  
  
    2.  <span data-ttu-id="0f130-108"><BizTalk_install>\HttpReceive に移動し、これを SSO プロジェクト</span><span class="sxs-lookup"><span data-stu-id="0f130-108">Browse to and copy <BizTalk_install>\HttpReceive to the folder containing your SSO project, for example,</span></span>  
  
         <span data-ttu-id="0f130-109">(<Adapter_install>\biztalk2010\SSO\mySSODemo\BTSHTTPReceive.dll など) を格納しているフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="0f130-109"><Adapter_install>\biztalk2010\SSO\mySSODemo\BTSHTTPReceive.dll.</span></span>  
  
    3.  <span data-ttu-id="0f130-110">MySSODemo Web サービス拡張機能の状態を設定**許可**です。</span><span class="sxs-lookup"><span data-stu-id="0f130-110">Set status of mySSODemo Web service extension to **Allowed**.</span></span>  
  
2.  <span data-ttu-id="0f130-111">IIS を再起動してすべての変更が反映されるようにします。</span><span class="sxs-lookup"><span data-stu-id="0f130-111">Restart IIS to ensure that all changes are in effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f130-112">参照</span><span class="sxs-lookup"><span data-stu-id="0f130-112">See Also</span></span>  
 [<span data-ttu-id="0f130-113">シングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="0f130-113">Using Single Sign-On</span></span>](../core/using-single-sign-on3.md)