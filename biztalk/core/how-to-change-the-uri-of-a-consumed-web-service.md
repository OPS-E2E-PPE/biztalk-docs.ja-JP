---
title: 使用する Web サービスの URI を変更する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, modifying
- Web services, consuming
- consuming [Web services]
- modifying, Web services
ms.assetid: 907de565-8c99-4d34-939f-fd3dba37dd11
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b9ae7d7178fc24c5f16b28325fb627045e5273a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247402"
---
# <a name="how-to-change-the-uri-of-a-consumed-web-service"></a><span data-ttu-id="0f0ba-102">使用する Web サービスの URI の変更方法</span><span class="sxs-lookup"><span data-stu-id="0f0ba-102">How to Change the URI of a Consumed Web Service</span></span>
<span data-ttu-id="0f0ba-103">オーケストレーションを展開すると、オーケストレーションが参照する各 Web サービスの送信ポートが BizTalk Server によって構成されます。</span><span class="sxs-lookup"><span data-stu-id="0f0ba-103">After you deploy your orchestration, BizTalk Server configures a send port for each Web service that the orchestration references.</span></span> <span data-ttu-id="0f0ba-104">既定では、実行時の Web サービスの URL が、インポートされた Web サービスの URL にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="0f0ba-104">By default, BizTalk uses the URL of the Web service at run time for the same URL for the imported Web service.</span></span> <span data-ttu-id="0f0ba-105">この URL は、BizTalk Server 管理コンソールを使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="0f0ba-105">You can change this URL using BizTalk Server Administration console.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0f0ba-106">オーケストレーションは、使用する Web サービスの URI を変更する前に展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f0ba-106">You must deploy your orchestration before you change the URI of a consumed Web service.</span></span> <span data-ttu-id="0f0ba-107">オーケストレーションの展開の詳細については、次を参照してください。 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="0f0ba-107">For more information on deploying your orchestration, see [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>  
  
### <a name="to-change-the-uri-of-a-consumed-web-service-using-biztalk-server-administration-console"></a><span data-ttu-id="0f0ba-108">使用する Web サービスの URI を BizTalk Server 管理コンソールで変更するには</span><span class="sxs-lookup"><span data-stu-id="0f0ba-108">To change the URI of a consumed Web service using BizTalk Server Administration Console</span></span>  
  
1.  <span data-ttu-id="0f0ba-109">BizTalk Server 管理コンソールで、BizTalk アプリケーションを展開し、展開、**送信ポート**ノード。</span><span class="sxs-lookup"><span data-stu-id="0f0ba-109">In BizTalk Server Administration console, expand a BizTalk application, and then expand the **Send Ports** node.</span></span>  
  
2.  <span data-ttu-id="0f0ba-110">SOAP アダプターで構成された送信ポートを右クリックし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="0f0ba-110">Right-click a send port configured with SOAP adapter, click **Properties**.</span></span>  
  
3.  <span data-ttu-id="0f0ba-111">物理ポートがあるない場合は、送信ポートを作成し、BizTalk 管理コンソールを使用して受信場所。</span><span class="sxs-lookup"><span data-stu-id="0f0ba-111">If you do not have physical ports, you can create send ports and receive locations by using BizTalk Administration console.</span></span> <span data-ttu-id="0f0ba-112">詳細については、次を参照してください。[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)です。</span><span class="sxs-lookup"><span data-stu-id="0f0ba-112">For information, see [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span>  
  
4.  <span data-ttu-id="0f0ba-113">**送信プロパティ**ダイアログ ボックスで、をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="0f0ba-113">On the **Send Properties** dialog box, click **Configure**.</span></span>  
  
5.  <span data-ttu-id="0f0ba-114">**SOAP トランスポートのプロパティ** ダイアログ ボックスで、 **Web サービス URL**ボックス、Web サービスの場所の完全な URL を入力し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="0f0ba-114">In the **SOAP Transport Properties** dialog box, in the **Web Service URL** box, type the full URL for the location of the Web service, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0f0ba-115">指定した URL に対応する Web サービスが存在することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0f0ba-115">You should ensure that a Web service exists for the URL that you specify.</span></span> <span data-ttu-id="0f0ba-116">BizTalk Server では URL の場所は検証されません。</span><span class="sxs-lookup"><span data-stu-id="0f0ba-116">BizTalk Server does not validate the URL location.</span></span>  
  
6.  <span data-ttu-id="0f0ba-117">終了するには、ok をクリックして、**送信プロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="0f0ba-117">Click OK to exit the **Send Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f0ba-118">参照</span><span class="sxs-lookup"><span data-stu-id="0f0ba-118">See Also</span></span>  
 <span data-ttu-id="0f0ba-119">[BizTalk Server 管理コンソールを使用します。](../core/using-the-biztalk-server-administration-console.md) </span><span class="sxs-lookup"><span data-stu-id="0f0ba-119">[Using the BizTalk Server Administration Console](../core/using-the-biztalk-server-administration-console.md) </span></span>  
 <span data-ttu-id="0f0ba-120">[SOAP 送信ポートを構成する方法](../core/how-to-configure-a-soap-send-port.md) </span><span class="sxs-lookup"><span data-stu-id="0f0ba-120">[How to Configure a SOAP Send Port](../core/how-to-configure-a-soap-send-port.md) </span></span>  
 <span data-ttu-id="0f0ba-121">[使用する Web サービスでの SOAP ヘッダー](../core/soap-headers-with-consumed-web-services.md) </span><span class="sxs-lookup"><span data-stu-id="0f0ba-121">[SOAP Headers with Consumed Web Services](../core/soap-headers-with-consumed-web-services.md) </span></span>  
 [<span data-ttu-id="0f0ba-122">Web ポートの作成</span><span class="sxs-lookup"><span data-stu-id="0f0ba-122">Creating Web Ports</span></span>](../core/creating-web-ports.md)