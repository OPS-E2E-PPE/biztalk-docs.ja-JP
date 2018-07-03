---
title: ソリューションを指向サービスをインストールする前に |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solution tutorial, deployment prerequisites
ms.assetid: 865bd21c-e49a-4647-af91-fefee07ee806
caps.latest.revision: 36
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3a735ed832051c24e5ccd253df61c42c07ed6e6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982387"
---
# <a name="before-installing-the-service-oriented-solution"></a><span data-ttu-id="82967-102">サービス指向ソリューションをインストールする前に</span><span class="sxs-lookup"><span data-stu-id="82967-102">Before Installing the Service Oriented Solution</span></span>
<span data-ttu-id="82967-103">単一のコンピューターにサービス指向ソリューションのスタブ バージョンをインストールするために必要な次のコンポーネントを用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82967-103">The following prerequisites must be available to install the stub version of the service-oriented solution on a single computer:</span></span>  
  
- [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)]<span data-ttu-id="82967-104">。</span><span class="sxs-lookup"><span data-stu-id="82967-104">.</span></span>  
  
- <span data-ttu-id="82967-105">[!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)] でサポートされているソフトウェア</span><span class="sxs-lookup"><span data-stu-id="82967-105">Supported software for [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)].</span></span>  
  
- <span data-ttu-id="82967-106">IBM WebSphere MQ Client for Windows の最新バージョン</span><span class="sxs-lookup"><span data-stu-id="82967-106">The latest version of IBM WebSphere MQ Client for Windows</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="82967-107">MQSeries Server は、このソリューションのスタブ バージョンで必要ありません。</span><span class="sxs-lookup"><span data-stu-id="82967-107">MQSeries Server is not required for the stub version of the solution.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="82967-108">IBM Web サイトから IBM WebSphere MQ Client for Windows をダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="82967-108">You can download IBM WebSphere MQ Client for Windows from the IBM Web site.</span></span>  
  
  <span data-ttu-id="82967-109">単一のコンピューターにサービス指向ソリューションのインライン バージョンおよびアダプター バージョンをインストールするには</span><span class="sxs-lookup"><span data-stu-id="82967-109">For installing the inline and adapter version of the service oriented solution on a single computer:</span></span>  
  
- [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)]<span data-ttu-id="82967-110">。</span><span class="sxs-lookup"><span data-stu-id="82967-110">.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="82967-111">ドメイン アカウントは、エンタープライズ シングル サインオン (SSO) の資格情報をマップするために必要です。</span><span class="sxs-lookup"><span data-stu-id="82967-111">A domain account is required to map credentials for Enterprise Single Sign-On (SSO).</span></span> <span data-ttu-id="82967-112">BizTalk サービス用のドメイン アカウントおよび ENTSSO サービス アカウント用のドメイン アカウントを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="82967-112">We recommend using domain accounts for the BizTalk service and for the ENTSSO service accounts.</span></span>  
  
- <span data-ttu-id="82967-113">[!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)] でサポートされているソフトウェア</span><span class="sxs-lookup"><span data-stu-id="82967-113">Supported software for [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)].</span></span>  
  
- <span data-ttu-id="82967-114">ローカル コンピューター上の MQSeries Server または MQSeries Server を実行しているコンピューターへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="82967-114">MQSeries Server on the local computer or access to the computer running the MQSeries Server.</span></span> <span data-ttu-id="82967-115">インライン バージョンを使用する場合、このソリューションのオーケストレーションを実行している BizTalk Server 上に MQSeries クライアント API を用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82967-115">For the inline version, MQSeries client APIs must be available on the BizTalk server running the solution’s orchestrations.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="82967-116">MQSeries Server のバージョンは、BizTalk Server の MQSeries アダプタで必要なバージョンに一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82967-116">The version of MQSeries Server must match the version required by the BizTalk Server MQSeries Adapter.</span></span> <span data-ttu-id="82967-117">これにより、フィックス パック (CSD10) が適用されている IBM WebSphere MQ for Windows のバージョン 5.3 以降を使用できます。</span><span class="sxs-lookup"><span data-stu-id="82967-117">This can include IBM WebSphere MQ for Windows Version 5.3 with Fix Pack 10 (CSD10) or later.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="82967-118">分散コンポーネント オブジェクト モデル (DCOM) によるサーバーの呼び出しを可能にする MQSeries などの機能を使用する際は、ネットワーク アドレス変換 (NAT) ベースのファイアウォールが無効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="82967-118">When using features such as MQSeries which make Distributed Component Object Model (DCOM) calls to the server, make sure you do not have a Network Address Translation (NAT)-based firewall enabled.</span></span> <span data-ttu-id="82967-119">クライアントは、実際の IP アドレスを使用してサーバーにアクセスできる必要があり、NAT ベースのファイアウォールによって、このアドレスはクライアントが認識できないように変換されます。</span><span class="sxs-lookup"><span data-stu-id="82967-119">The client must be able to access the server by its actual IP address, and NAT-based firewalls translate this address to something the client will not recognize.</span></span>  
  
- <span data-ttu-id="82967-120">メインフレームに必要なソリューションのバリエーションを使用している場合の CICS および Transaction X 対応の IBM メインフレーム。</span><span class="sxs-lookup"><span data-stu-id="82967-120">IBM Mainframe with CICS and Transaction X if you are using a variation of the solution that requires a mainframe.</span></span> <span data-ttu-id="82967-121">この場合、CICS アプリケーション (COBOL コード) をメインフレームにインストールする必要があります。また、メインフレームにアクセスするには、Microsoft Host Integration Server (HIS) が必要です。</span><span class="sxs-lookup"><span data-stu-id="82967-121">In this case, the CICS application (COBOL code) must be installed on the mainframe and Microsoft Host Integration Server (HIS) is required to access the mainframe.</span></span>  
  
   <span data-ttu-id="82967-122">このソリューションに対応するメインフレームがない場合、ポートのバインドを変更して、Pending Transactions のスタブ Web サービスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="82967-122">If you don’t have a mainframe for the solution, you can modify the port binding to use the stub Web service for Pending Transactions.</span></span> <span data-ttu-id="82967-123">メインフレームのトランザクションをエミュレートするため、Web サービスは、ローカルにトランザクションを生成します。</span><span class="sxs-lookup"><span data-stu-id="82967-123">The Web service generates transactions locally to emulate the mainframe transactions.</span></span> <span data-ttu-id="82967-124">スタブ Pending Transactions Web サービスのポートのバインドを変更する方法の詳細については、次を参照してください。[インライン バージョンおよびアダプター バージョンのサービス指向ソリューションのインストール方法](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md)します。</span><span class="sxs-lookup"><span data-stu-id="82967-124">For more information about how to modify the port binding for the stub Pending Transactions Web service, see [How to Install the Inline and Adapter Versions of the Service Oriented Solution](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md).</span></span>  
  
- <span data-ttu-id="82967-125">Host Integration Server は、メインフレームに接続するために必要です。</span><span class="sxs-lookup"><span data-stu-id="82967-125">Host Integration Server is required to connect to the mainframe.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="82967-126">Host Integration Server は、BizTalk Server の一部として含まれています。</span><span class="sxs-lookup"><span data-stu-id="82967-126">Host Integration Server is included as part of BizTalk Server.</span></span>  
  
- <span data-ttu-id="82967-127">HTTPS 接続に使用する証明書を構成した Web サーバー。</span><span class="sxs-lookup"><span data-stu-id="82967-127">Web server configured with a certificate for HTTPS connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82967-128">参照</span><span class="sxs-lookup"><span data-stu-id="82967-128">See Also</span></span>  
 <span data-ttu-id="82967-129">[指向ソリューションのスタブ バージョンのサービスをインストールする方法](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="82967-129">[How to Install the Stub Version of the Service Oriented Solution](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="82967-130">[指向ソリューションのインライン バージョンおよびアダプター バージョンのサービスをインストールする方法](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="82967-130">[How to Install the Inline and Adapter Versions of the Service Oriented Solution](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="82967-131">[指向ソリューションのサービスを実行する方法](../core/how-to-run-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="82967-131">[How to Run the Service Oriented Solution](../core/how-to-run-the-service-oriented-solution.md) </span></span>  
 [<span data-ttu-id="82967-132">サービス指向ソリューションに対する開発者のコンピューター設定</span><span class="sxs-lookup"><span data-stu-id="82967-132">Developer Machine Setup for the Service Oriented Solution</span></span>](../core/developer-machine-setup-for-the-service-oriented-solution.md)