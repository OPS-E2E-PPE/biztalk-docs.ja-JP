---
title: HTTP 受信 Adapter2 を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP receive adapter, configuring
- configuring HTTP receive adapter
ms.assetid: dd26fd57-90d8-4ffe-b56f-8de55ecc6f68
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a73b04356f7c09d8aa2a24d816f02dc66e5d414d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340840"
---
# <a name="how-to-configure-the-http-receive-adapter"></a><span data-ttu-id="e2d1a-102">HTTP 受信アダプターを構成する方法</span><span class="sxs-lookup"><span data-stu-id="e2d1a-102">How to Configure the HTTP Receive Adapter</span></span>
<span data-ttu-id="e2d1a-103">HTTP を使用する受信アダプターは BizTalk Server にメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="e2d1a-103">You can use the HTTP receive adapter to submit messages to BizTalk Server.</span></span> <span data-ttu-id="e2d1a-104">HTTP 受信アダプターは IIS プロセスでホストされているインターネット インフォメーション サービス (IIS) の ISAPI 拡張機能。</span><span class="sxs-lookup"><span data-stu-id="e2d1a-104">The HTTP receive adapter is an Internet Information Services (IIS) ISAPI extension that is hosted in the IIS process.</span></span>  
  
### <a name="to-configure-the-http-receive-adapter"></a><span data-ttu-id="e2d1a-105">HTTP 受信アダプターを構成するには</span><span class="sxs-lookup"><span data-stu-id="e2d1a-105">To configure the HTTP receive adapter</span></span>  
  
1.  <span data-ttu-id="e2d1a-106">Http 受信アダプター (BTSHTTPReceive.dll)  **\<BizTalk2010 > \HttpReceive >** シングル サインオン (SSO) プロジェクトが含まれるフォルダーに (たとえば、 **< Adapter_install > \biztalk2010\SSO\mySSODemo**)。</span><span class="sxs-lookup"><span data-stu-id="e2d1a-106">Copy the HTTP receive adapter (BTSHTTPReceive.dll) from **\<BizTalk2010>\HttpReceive>** to the folder containing your Single Sign-On (SSO) project (for example, **<Adapter_install>\biztalk2010\SSO\mySSODemo**).</span></span>  
  
    1.  <span data-ttu-id="e2d1a-107">新しい Web サービス拡張機能 mySSODemo を追加します。</span><span class="sxs-lookup"><span data-stu-id="e2d1a-107">Add a new Web service extension mySSODemo.</span></span>  
  
    2.  <span data-ttu-id="e2d1a-108">参照して、たとえば、SSO プロジェクトが含まれるフォルダーにコピー < BizTalk_install > \HttpReceive</span><span class="sxs-lookup"><span data-stu-id="e2d1a-108">Browse to and copy <BizTalk_install>\HttpReceive to the folder containing your SSO project, for example,</span></span>  
  
         <span data-ttu-id="e2d1a-109"><Adapter_install>\biztalk2010\SSO\mySSODemo\BTSHTTPReceive.dll.</span><span class="sxs-lookup"><span data-stu-id="e2d1a-109"><Adapter_install>\biztalk2010\SSO\mySSODemo\BTSHTTPReceive.dll.</span></span>  
  
    3.  <span data-ttu-id="e2d1a-110">MySSODemo Web サービス拡張の状態を設定**許可**します。</span><span class="sxs-lookup"><span data-stu-id="e2d1a-110">Set status of mySSODemo Web service extension to **Allowed**.</span></span>  
  
2.  <span data-ttu-id="e2d1a-111">すべての変更が有効なことを確認するには、次のように IIS を再起動します。</span><span class="sxs-lookup"><span data-stu-id="e2d1a-111">Restart IIS to ensure that all changes are in effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2d1a-112">参照</span><span class="sxs-lookup"><span data-stu-id="e2d1a-112">See Also</span></span>  
 [<span data-ttu-id="e2d1a-113">アダプターのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="e2d1a-113">Security in the adapter</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)