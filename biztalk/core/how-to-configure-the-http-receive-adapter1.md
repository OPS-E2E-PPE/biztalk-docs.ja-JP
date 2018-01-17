---
title: "HTTP 受信 Adapter1 を構成する方法 |Microsoft ドキュメント"
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
ms.assetid: e7dbfed3-9dd8-49c9-90b6-a655d7c5446f
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c18cdcad8deaa9cd76930b91e94860c99749f78
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-configure-the-http-receive-adapter"></a><span data-ttu-id="94dbb-102">HTTP 受信アダプターを構成する方法</span><span class="sxs-lookup"><span data-stu-id="94dbb-102">How to Configure the HTTP Receive Adapter</span></span>
<span data-ttu-id="94dbb-103">HTTP 受信アダプターを使用して [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="94dbb-103">You can use the HTTP receive adapter to submit messages to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="94dbb-104">HTTP 受信アダプターは、インターネット インフォメーション サービス (IIS) プロセスでホストされる IIS の ISAPI 拡張です。</span><span class="sxs-lookup"><span data-stu-id="94dbb-104">The HTTP receive adapter is an Internet Information Services (IIS) ISAPI extension that is hosted in the IIS process.</span></span>  
  
### <a name="to-configure-the-http-receive-adapter"></a><span data-ttu-id="94dbb-105">HTTP 受信アダプターを構成するには</span><span class="sxs-lookup"><span data-stu-id="94dbb-105">To configure the HTTP receive adapter</span></span>  
  
1.  <span data-ttu-id="94dbb-106">HTTP 受信アダプター (BTSHTTPReceive.dll) から **\<BizTalk\>\HttpReceive\>** など、シングル サインオン (SSO) プロジェクトが含まれているフォルダーに。</span><span class="sxs-lookup"><span data-stu-id="94dbb-106">Copy the HTTP receive adapter (BTSHTTPReceive.dll) from **\<BizTalk\>\HttpReceive\>** to the folder that contains your Single Sign-On (SSO) project, for example:</span></span>  
  
     <span data-ttu-id="94dbb-107">**< Adapter_install > \biztalk\SSO\mySSODemo**</span><span class="sxs-lookup"><span data-stu-id="94dbb-107">**<Adapter_install>\biztalk\SSO\mySSODemo**</span></span>  
  
    1.  <span data-ttu-id="94dbb-108">新しい Web サービス拡張機能 mySSODemo を追加します。</span><span class="sxs-lookup"><span data-stu-id="94dbb-108">Add a new Web service extension mySSODemo.</span></span>  
  
    2.  <span data-ttu-id="94dbb-109">見つけてコピー **< BizTalk_install > \HttpReceive** を SSO プロジェクトを次に例を含むフォルダーにします。</span><span class="sxs-lookup"><span data-stu-id="94dbb-109">Locate and copy **<BizTalk_install>\HttpReceive** to the folder that contains your SSO project, for example:</span></span>  
  
         <span data-ttu-id="94dbb-110">**< Adapter_install > \biztalk\SSO\mySSODemo\BTSHTTPReceive.dll します。**</span><span class="sxs-lookup"><span data-stu-id="94dbb-110">**<Adapter_install>\biztalk\SSO\mySSODemo\BTSHTTPReceive.dll.**</span></span>  
  
    3.  <span data-ttu-id="94dbb-111">MySSODemo Web サービス拡張の状態を設定 **許可**します。</span><span class="sxs-lookup"><span data-stu-id="94dbb-111">Set the status of mySSODemo Web service extension to **Allowed**.</span></span>  
  
2.  <span data-ttu-id="94dbb-112">IIS を再起動して、すべての変更内容を適用します。</span><span class="sxs-lookup"><span data-stu-id="94dbb-112">Restart IIS to apply all changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94dbb-113">参照</span><span class="sxs-lookup"><span data-stu-id="94dbb-113">See Also</span></span>  
 [<span data-ttu-id="94dbb-114">アダプターのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="94dbb-114">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)