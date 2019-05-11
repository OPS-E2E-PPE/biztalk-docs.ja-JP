---
title: Web サービスを公開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, publishing
- BizTalk Server Web Services Publishing Wizard
ms.assetid: eed0717c-b390-492a-a3b9-ae31024805a2
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76c699ff7fec169064b446e0e83b9eaae1160bfd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398351"
---
# <a name="publishing-web-services"></a><span data-ttu-id="c7410-102">Web サービスの公開</span><span class="sxs-lookup"><span data-stu-id="c7410-102">Publishing Web Services</span></span>
<span data-ttu-id="c7410-103">Web サービスを公開するには、オーケストレーションやその他の送信アダプターで使用する Microsoft BizTalk Server にメッセージを送信できる Web サービスを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="c7410-103">Publishing Web services enables you to create a Web service that can submit messages to Microsoft BizTalk Server for use by orchestrations and other send adapters.</span></span> <span data-ttu-id="c7410-104">BizTalk Web サービス公開ウィザードを使用して、公開済み Web サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="c7410-104">You create published Web services using the BizTalk Web Services Publishing Wizard.</span></span> <span data-ttu-id="c7410-105">SOAP 送信ハンドラーの構成方法の詳細については、次を参照してください。 [SOAP 送信ハンドラーを構成する方法](../core/how-to-configure-a-soap-send-handler.md)します。</span><span class="sxs-lookup"><span data-stu-id="c7410-105">For information about configuring a SOAP send handler, see [How to Configure a SOAP Send Handler](../core/how-to-configure-a-soap-send-handler.md).</span></span> <span data-ttu-id="c7410-106">SOAP 送信ポートの構成方法の詳細については、次を参照してください。 [SOAP 送信ポートを構成する方法](../core/how-to-configure-a-soap-send-port.md)します。</span><span class="sxs-lookup"><span data-stu-id="c7410-106">For information about configuring a SOAP send port, see [How to Configure a SOAP Send Port](../core/how-to-configure-a-soap-send-port.md).</span></span>  
  
 <span data-ttu-id="c7410-107">BizTalk Web サービス公開ウィザードによって Web サービスに公開する 2 つのメソッドを提供します。 Web サービスとしてのオーケストレーションの公開とスキーマを Web サービスとして公開します。</span><span class="sxs-lookup"><span data-stu-id="c7410-107">The BizTalk Web Services Publishing Wizard provides you with two methods to publish Web services: publishing an orchestration as a Web service and publishing schemas as a Web service.</span></span>  
  
 <span data-ttu-id="c7410-108">インストールし、Microsoft BizTalk Server のオーケストレーションとスキーマを Web サービスとして公開する前に、Microsoft インターネット インフォメーション サービス (IIS) と ASP.NET を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7410-108">You must install and enable Microsoft Internet Information Services (IIS) and ASP.NET before you can publish Microsoft BizTalk Server orchestrations and schemas as Web services.</span></span> <span data-ttu-id="c7410-109">IIS と ASP.NET のインストール方法の詳細については、インストールするインターネット インフォメーション サービス (IIS) にある BizTalk Server インストール ガイドを参照してください。 [HYPERLINK"http://go.microsoft.com/fwlink/?LinkID=191321" http://go.microsoft.com/fwlink/?LinkID=191321](http://go.microsoft.com/fwlink/?LinkID=191321)します。</span><span class="sxs-lookup"><span data-stu-id="c7410-109">For information about installing IIS and ASP.NET, see Installing Internet Information Services (IIS) in the BizTalk Server Installation Guide located at [HYPERLINK "http://go.microsoft.com/fwlink/?LinkID=191321" http://go.microsoft.com/fwlink/?LinkID=191321](http://go.microsoft.com/fwlink/?LinkID=191321).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c7410-110">BizTalk Web サービス公開ウィザードを実行する前に、Web サービスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7410-110">Before running the BizTalk Web Services Publishing Wizard, you must enable Web services.</span></span> <span data-ttu-id="c7410-111">お使いのシステムの Web サービスを有効にする方法の詳細については、次を参照してください。 [Web サービスを有効にする](../core/enabling-web-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="c7410-111">For more information about enabling Web services for your system, see [Enabling Web Services](../core/enabling-web-services.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c7410-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c7410-112">In This Section</span></span>  
  
-   [<span data-ttu-id="c7410-113">Web サービスを公開するための計画</span><span class="sxs-lookup"><span data-stu-id="c7410-113">Planning for Publishing Web Services</span></span>](../core/planning-for-publishing-web-services2.md)  
  
-   [<span data-ttu-id="c7410-114">Web サービスの有効化</span><span class="sxs-lookup"><span data-stu-id="c7410-114">Enabling Web Services</span></span>](../core/enabling-web-services.md)  
  
-   [<span data-ttu-id="c7410-115">Web サービスとしてのオーケストレーションの公開</span><span class="sxs-lookup"><span data-stu-id="c7410-115">Publishing an Orchestration as a Web Service</span></span>](../core/publishing-an-orchestration-as-a-web-service.md)  
  
-   [<span data-ttu-id="c7410-116">Web サービスとしてのスキーマの公開</span><span class="sxs-lookup"><span data-stu-id="c7410-116">Publishing Schemas as a Web Service</span></span>](../core/publishing-schemas-as-a-web-service.md)  
  
-   [<span data-ttu-id="c7410-117">Web サービスを公開する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="c7410-117">Considerations When Publishing Web Services</span></span>](../core/considerations-when-publishing-web-services.md)  
  
-   [<span data-ttu-id="c7410-118">公開済み Web サービスのデバッグ</span><span class="sxs-lookup"><span data-stu-id="c7410-118">Debugging Published Web Services</span></span>](../core/debugging-published-web-services.md)  
  
-   [<span data-ttu-id="c7410-119">公開済み Web サービスのテスト</span><span class="sxs-lookup"><span data-stu-id="c7410-119">Testing Published Web Services</span></span>](../core/testing-published-web-services.md)  
  
-   [<span data-ttu-id="c7410-120">Visual Studio がインストールされていないコンピューターへの公開済み Web サービスの展開</span><span class="sxs-lookup"><span data-stu-id="c7410-120">Deploying Published Web Services on a Non-Visual Studio Computer</span></span>](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)