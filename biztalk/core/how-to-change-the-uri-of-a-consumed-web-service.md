---
title: 使用する Web サービスの URI を変更する方法 |Microsoft Docs
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
ms.openlocfilehash: c5fd101ba0553397b6c7144545a9ac557ceada03
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342390"
---
# <a name="how-to-change-the-uri-of-a-consumed-web-service"></a><span data-ttu-id="178fb-102">使用する Web サービスの URI の変更方法</span><span class="sxs-lookup"><span data-stu-id="178fb-102">How to Change the URI of a Consumed Web Service</span></span>
<span data-ttu-id="178fb-103">オーケストレーションを展開した後、BizTalk Server は、オーケストレーションが参照される各 Web サービス用の送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="178fb-103">After you deploy your orchestration, BizTalk Server configures a send port for each Web service that the orchestration references.</span></span> <span data-ttu-id="178fb-104">既定では、BizTalk は、実行時にインポートされた Web サービスに対する同じ URL の Web サービスの URL を使用します。</span><span class="sxs-lookup"><span data-stu-id="178fb-104">By default, BizTalk uses the URL of the Web service at run time for the same URL for the imported Web service.</span></span> <span data-ttu-id="178fb-105">BizTalk Server 管理コンソールを使用して、この URL を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="178fb-105">You can change this URL using BizTalk Server Administration console.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="178fb-106">使用する Web サービスの URI を変更する前に、オーケストレーションを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="178fb-106">You must deploy your orchestration before you change the URI of a consumed Web service.</span></span> <span data-ttu-id="178fb-107">オーケストレーションの展開の詳細については、次を参照してください。 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="178fb-107">For more information on deploying your orchestration, see [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>  
  
### <a name="to-change-the-uri-of-a-consumed-web-service-using-biztalk-server-administration-console"></a><span data-ttu-id="178fb-108">BizTalk Server 管理コンソールを使用して使用する Web サービスの URI を変更するには</span><span class="sxs-lookup"><span data-stu-id="178fb-108">To change the URI of a consumed Web service using BizTalk Server Administration Console</span></span>  
  
1.  <span data-ttu-id="178fb-109">BizTalk Server 管理コンソールで、BizTalk アプリケーションを展開し、展開、**送信ポート**ノード。</span><span class="sxs-lookup"><span data-stu-id="178fb-109">In BizTalk Server Administration console, expand a BizTalk application, and then expand the **Send Ports** node.</span></span>  
  
2.  <span data-ttu-id="178fb-110">SOAP アダプターで構成された送信ポートを右クリックし、をクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="178fb-110">Right-click a send port configured with SOAP adapter, click **Properties**.</span></span>  
  
3.  <span data-ttu-id="178fb-111">物理ポートがいない場合は、送信ポートを作成し、BizTalk 管理コンソールを使用して受信場所。</span><span class="sxs-lookup"><span data-stu-id="178fb-111">If you do not have physical ports, you can create send ports and receive locations by using BizTalk Administration console.</span></span> <span data-ttu-id="178fb-112">詳しくは、次を参照してください。[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)します。</span><span class="sxs-lookup"><span data-stu-id="178fb-112">For information, see [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span>  
  
4.  <span data-ttu-id="178fb-113">**送信プロパティ**ダイアログ ボックスで、をクリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="178fb-113">On the **Send Properties** dialog box, click **Configure**.</span></span>  
  
5.  <span data-ttu-id="178fb-114">**SOAP トランスポートのプロパティ** ダイアログ ボックスで、 **Web サービスの URL**ボックスに、Web サービスの場所の完全な URL を入力し、 をクリックして**OK**。</span><span class="sxs-lookup"><span data-stu-id="178fb-114">In the **SOAP Transport Properties** dialog box, in the **Web Service URL** box, type the full URL for the location of the Web service, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="178fb-115">指定された URL の Web サービスが存在することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="178fb-115">You should ensure that a Web service exists for the URL that you specify.</span></span> <span data-ttu-id="178fb-116">BizTalk Server では、URL の場所は検証されません。</span><span class="sxs-lookup"><span data-stu-id="178fb-116">BizTalk Server does not validate the URL location.</span></span>  
  
6.  <span data-ttu-id="178fb-117">終了するには、ok をクリックして、**送信プロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="178fb-117">Click OK to exit the **Send Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="178fb-118">参照</span><span class="sxs-lookup"><span data-stu-id="178fb-118">See Also</span></span>  
 <span data-ttu-id="178fb-119">[BizTalk Server 管理コンソールの使用](../core/using-the-biztalk-server-administration-console.md) </span><span class="sxs-lookup"><span data-stu-id="178fb-119">[Using the BizTalk Server Administration Console](../core/using-the-biztalk-server-administration-console.md) </span></span>  
 <span data-ttu-id="178fb-120">[SOAP 送信ポートを構成する方法](../core/how-to-configure-a-soap-send-port.md) </span><span class="sxs-lookup"><span data-stu-id="178fb-120">[How to Configure a SOAP Send Port](../core/how-to-configure-a-soap-send-port.md) </span></span>  
 <span data-ttu-id="178fb-121">[消費済み Web サービスでの SOAP ヘッダー](../core/soap-headers-with-consumed-web-services.md) </span><span class="sxs-lookup"><span data-stu-id="178fb-121">[SOAP Headers with Consumed Web Services](../core/soap-headers-with-consumed-web-services.md) </span></span>  
 [<span data-ttu-id="178fb-122">Web ポートの作成</span><span class="sxs-lookup"><span data-stu-id="178fb-122">Creating Web Ports</span></span>](../core/creating-web-ports.md)