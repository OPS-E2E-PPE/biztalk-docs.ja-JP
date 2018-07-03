---
title: サンプル シナリオの情報をバック グラウンド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security examples [TMA], background information
- DFD
- TMA, examples
ms.assetid: f9518fe7-9892-44f5-8e05-fe48bdb5161a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9424de9c530fb855b21df787f87e674e8a561f5e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978451"
---
# <a name="background-information-for-sample-scenarios"></a><span data-ttu-id="92d6e-102">サンプル シナリオの背景情報</span><span class="sxs-lookup"><span data-stu-id="92d6e-102">Background Information for Sample Scenarios</span></span>
<span data-ttu-id="92d6e-103">このトピックには、このセクションで紹介するシナリオの背景情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="92d6e-103">This topic contains background information for the scenarios in this section.</span></span>  
  
## <a name="background-for-all-scenarios"></a><span data-ttu-id="92d6e-104">すべてのシナリオの背景</span><span class="sxs-lookup"><span data-stu-id="92d6e-104">Background for all scenarios</span></span>  
 <span data-ttu-id="92d6e-105">主要な脅威モデルについてのミーティングを行う前に、次の背景情報を収集しました。</span><span class="sxs-lookup"><span data-stu-id="92d6e-105">Before the main threat model meeting, we collected the following background information.</span></span> <span data-ttu-id="92d6e-106">この情報は、サンプル アーキテクチャで特定されたすべての使用シナリオに適用されます。</span><span class="sxs-lookup"><span data-stu-id="92d6e-106">This information applies to all the usage scenarios we identified for the sample architecture:</span></span>  
  
-   <span data-ttu-id="92d6e-107">アーキテクチャの境界およびスコープ</span><span class="sxs-lookup"><span data-stu-id="92d6e-107">Boundaries and scope of the architecture</span></span>  
  
-   <span data-ttu-id="92d6e-108">信頼されたコンポーネントと信頼されていないコンポーネントの境界</span><span class="sxs-lookup"><span data-stu-id="92d6e-108">Boundaries between trusted and untrusted components</span></span>  
  
-   <span data-ttu-id="92d6e-109">各コンポーネントの構成および管理モデル</span><span class="sxs-lookup"><span data-stu-id="92d6e-109">Configuration and administration model for each component</span></span>  
  
-   <span data-ttu-id="92d6e-110">他のコンポーネントおよびアプリケーションに関する前提</span><span class="sxs-lookup"><span data-stu-id="92d6e-110">Assumptions about other components and applications</span></span>  
  
### <a name="boundaries-and-scope-of-the-architecture"></a><span data-ttu-id="92d6e-111">アーキテクチャの境界およびスコープ</span><span class="sxs-lookup"><span data-stu-id="92d6e-111">Boundaries and scope of the architecture</span></span>  
  
-   <span data-ttu-id="92d6e-112">ファイアウォール 2 により、E ビジネス ドメイン内のサーバーとアプリケーションを境界ネットワークおよび環境内の他のドメイン (企業ドメインや他のアプリケーションのドメインなど) から保護できます。</span><span class="sxs-lookup"><span data-stu-id="92d6e-112">Firewall 2 helps protect the servers and applications in the E-Business domain both from the perimeter network and from any other domains in your environment (for example, a corporate domain or domains for other applications).</span></span>  
  
-   <span data-ttu-id="92d6e-113">ファイアウォール 2 から E ビジネス ドメインにすべての着信トラフィックと送信トラフィックがルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="92d6e-113">Firewall 2 routes all incoming and outgoing traffic to the E-Business domain.</span></span>  
  
-   <span data-ttu-id="92d6e-114">BizTalk Server 環境にアクセスするすべてのユーザー グループとアカウントは E ビジネス ドメイン内のグローバル グループに属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="92d6e-114">All user groups and accounts that access the BizTalk Server environment must be global groups in the E-Business domain.</span></span>  
  
-   <span data-ttu-id="92d6e-115">アクセスは、ホスト インスタンスのサービス アカウントと、ファイル、SQL、またはメッセージ キューの受信サーバーにメッセージをドロップする任意のアプリケーション、および BizTalk Server、エンタープライズ シングル サインオン (SSO)、Windows の管理者に制限されます。</span><span class="sxs-lookup"><span data-stu-id="92d6e-115">Access is limited to the service account for the host instance; any applications that drop messages in the receive server for File, SQL, or Message Queuing; and administrators for BizTalk Server, Enterprise Single Sign-On (SSO), and Windows.</span></span>  
  
### <a name="boundaries-between-trusted-and-untrusted-companies"></a><span data-ttu-id="92d6e-116">信頼された企業と信頼されていない企業の境界</span><span class="sxs-lookup"><span data-stu-id="92d6e-116">Boundaries between trusted and untrusted companies</span></span>  
  
-   <span data-ttu-id="92d6e-117">ファイアウォール 2 から E ビジネス ドメインにすべての着信トラフィックと送信トラフィックがルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="92d6e-117">Firewall 2 routes all incoming and outgoing traffic to the E-Business domain.</span></span>  
  
-   <span data-ttu-id="92d6e-118">BizTalk Server 内のアプリケーション間でセキュリティの境界としてさまざまな BizTalk ホストを使用します。</span><span class="sxs-lookup"><span data-stu-id="92d6e-118">Use different BizTalk Hosts as a security boundary between applications within BizTalk Server.</span></span>  
  
-   <span data-ttu-id="92d6e-119">アプリケーション内のコードを信頼する場合に限り、信頼されたホストを使用します (たとえば、信頼されたホストではサード パーティ コンポーネントを実行しないでください)。</span><span class="sxs-lookup"><span data-stu-id="92d6e-119">Use trusted hosts only when you trust the code within the application (for example, do not run third-party components in a trusted host).</span></span>  
  
### <a name="configuration-and-administration-model-for-each-component"></a><span data-ttu-id="92d6e-120">各コンポーネントの構成および管理モデル</span><span class="sxs-lookup"><span data-stu-id="92d6e-120">Configuration and administration model for each component</span></span>  
 <span data-ttu-id="92d6e-121">**構成モデル:**</span><span class="sxs-lookup"><span data-stu-id="92d6e-121">**Configuration model:**</span></span>  
  
- <span data-ttu-id="92d6e-122">BizTalk Server ランタイム コンポーネントは、BizTalk Server のみにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="92d6e-122">BizTalk Server runtime components are installed only on the BizTalk Servers.</span></span>  
  
- <span data-ttu-id="92d6e-123">マスタ シークレット サーバーには追加コンポーネントはありません。</span><span class="sxs-lookup"><span data-stu-id="92d6e-123">Master secret server has no additional components.</span></span>  
  
- <span data-ttu-id="92d6e-124">SQL Server には、すべての BizTalk Server データベースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="92d6e-124">SQL Server contains all BizTalk Server databases.</span></span>  
  
- <span data-ttu-id="92d6e-125">境界ネットワーク内のサーバーには、BizTalk Server コンポーネントはありません。</span><span class="sxs-lookup"><span data-stu-id="92d6e-125">Servers in the perimeter networks do not have any BizTalk Server components.</span></span>  
  
- <span data-ttu-id="92d6e-126">管理クライアントは、E ビジネス ドメイン内のすべてのサーバーを管理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="92d6e-126">Administration client is used to administer all servers in the E-Business domain.</span></span>  
  
  <span data-ttu-id="92d6e-127">**管理モデル:**</span><span class="sxs-lookup"><span data-stu-id="92d6e-127">**Administration model:**</span></span>  
  
- <span data-ttu-id="92d6e-128">管理者は、デスクトップ (またはラップトップ) から管理ツールがあるコンピュータに (ターミナル サービスまたはリモート デスクトップ接続を使用して) 接続します。</span><span class="sxs-lookup"><span data-stu-id="92d6e-128">From a desktop (or laptop), an administrator connects to the computer that has the administration tools (using either Terminal Services or Remote Desktop connection).</span></span> <span data-ttu-id="92d6e-129">管理者は管理ツールのあるコンピュータに接続した後、BizTalk 管理ツールを使用してドメイン内のすべてのサーバーとアプリケーションを管理できます。</span><span class="sxs-lookup"><span data-stu-id="92d6e-129">After the administrator connects to the computer that has the administration tools, the administrator can use the BizTalk Administration tools to manage all servers and applications within the domain.</span></span>  
  
### <a name="assumptions-about-other-components-and-applications"></a><span data-ttu-id="92d6e-130">他のコンポーネントおよびアプリケーションに関する前提</span><span class="sxs-lookup"><span data-stu-id="92d6e-130">Assumptions about other components and applications</span></span>  
 <span data-ttu-id="92d6e-131">BizTalk Server 環境と連携する他のすべてのアプリケーションとコンポーネントは、E ビジネス ドメイン以外のドメイン (境界ネットワークなど) にあります。</span><span class="sxs-lookup"><span data-stu-id="92d6e-131">All other applications and components that interact with the BizTalk Server environment are in a domain other than the E-Business domain (for example, in a perimeter network).</span></span> <span data-ttu-id="92d6e-132">これらのアプリケーションとコンポーネント、および BizTalk Server 環境からのトラフィックは、ファイアウォール 2 経由で処理されます。</span><span class="sxs-lookup"><span data-stu-id="92d6e-132">The traffic from those applications and components to and from the BizTalk Server environment goes through Firewall 2.</span></span>  
  
 <span data-ttu-id="92d6e-133">BizTalk Server のサード パーティ アプリケーションの製造元は、信頼されたベンダです。</span><span class="sxs-lookup"><span data-stu-id="92d6e-133">Any third-party applications for BizTalk Server come from a trusted vendor.</span></span>  
  
### <a name="data-flow-diagrams"></a><span data-ttu-id="92d6e-134">データ フロー ダイアグラム</span><span class="sxs-lookup"><span data-stu-id="92d6e-134">Data flow diagrams</span></span>  
 <span data-ttu-id="92d6e-135">各使用シナリオの背景情報の最後の要素は、データ フロー ダイアグラム (DFD) です。</span><span class="sxs-lookup"><span data-stu-id="92d6e-135">The final element of background information for each usage scenario is a data flow diagram (DFD).</span></span> <span data-ttu-id="92d6e-136">DFD は、アーキテクチャ内のデータ フローがどのようなものであるかを示します。</span><span class="sxs-lookup"><span data-stu-id="92d6e-136">A DFD illustrates how data flows through the architecture.</span></span> <span data-ttu-id="92d6e-137">各シナリオには個別の DFD があります。</span><span class="sxs-lookup"><span data-stu-id="92d6e-137">Each scenario has a different DFD.</span></span> <span data-ttu-id="92d6e-138">このドキュメントのデータ フロー ダイアグラムには、次の図に示されている要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="92d6e-138">In this document, the data flow diagrams contain the elements shown in the following figure.</span></span>  
  
 <span data-ttu-id="92d6e-139">**図 1 DFD の要素**</span><span class="sxs-lookup"><span data-stu-id="92d6e-139">**Figure 1 Elements of the DFD**</span></span>  
  
 <span data-ttu-id="92d6e-140">![DFD の要素](../core/media/tdi-sec-dfd-legend.gif "TDI_Sec_DFD_Legend")</span><span class="sxs-lookup"><span data-stu-id="92d6e-140">![Elements of the DFD](../core/media/tdi-sec-dfd-legend.gif "TDI_Sec_DFD_Legend")</span></span>  
  
## <a name="background-for-adapter-scenarios"></a><span data-ttu-id="92d6e-141">アダプタ シナリオの背景</span><span class="sxs-lookup"><span data-stu-id="92d6e-141">Background for adapter scenarios</span></span>  
 <span data-ttu-id="92d6e-142">サンプル アーキテクチャでは、追加設定なしで使用できるいくつかのアダプタに基づく次の使用シナリオが特定されました。</span><span class="sxs-lookup"><span data-stu-id="92d6e-142">In our sample architecture, we identified the following usage scenarios based on some of the adapters you can use out-of-the-box:</span></span>  
  
- <span data-ttu-id="92d6e-143">HTTP アダプタと SOAP (Web サービス) アダプタ シナリオ</span><span class="sxs-lookup"><span data-stu-id="92d6e-143">HTTP and SOAP (Web services) adapters scenario</span></span>  
  
- <span data-ttu-id="92d6e-144">BizTalk メッセージ キュー アダプタ シナリオ</span><span class="sxs-lookup"><span data-stu-id="92d6e-144">BizTalk Message Queuing adapter scenario</span></span>  
  
- <span data-ttu-id="92d6e-145">ファイル アダプタ シナリオ</span><span class="sxs-lookup"><span data-stu-id="92d6e-145">File adapter scenario</span></span>  
  
- <span data-ttu-id="92d6e-146">FTP アダプタ シナリオ</span><span class="sxs-lookup"><span data-stu-id="92d6e-146">FTP adapter scenario</span></span>  
  
  <span data-ttu-id="92d6e-147">各シナリオでは、次の手順に従って脅威モデル分析を完了しました。</span><span class="sxs-lookup"><span data-stu-id="92d6e-147">For each scenario, we followed these steps to complete the threat model analysis:</span></span>  
  
- <span data-ttu-id="92d6e-148">背景情報の収集</span><span class="sxs-lookup"><span data-stu-id="92d6e-148">Collect background information</span></span>  
  
- <span data-ttu-id="92d6e-149">脅威モデルの作成と分析</span><span class="sxs-lookup"><span data-stu-id="92d6e-149">Create and analyze the threat model</span></span>  
  
- <span data-ttu-id="92d6e-150">脅威の確認</span><span class="sxs-lookup"><span data-stu-id="92d6e-150">Review threats</span></span>  
  
- <span data-ttu-id="92d6e-151">緩和方法とテクノロジの特定</span><span class="sxs-lookup"><span data-stu-id="92d6e-151">Identify mitigation techniques and technologies</span></span>  
  
  <span data-ttu-id="92d6e-152">各シナリオに対して、さまざまな攻撃によって生じる可能性がある脅威のレベルに応じて、一般的な度合いの策定を試みました。</span><span class="sxs-lookup"><span data-stu-id="92d6e-152">For each scenario, we have tried to develop generic ratings of the level of threat that the various attacks might represent.</span></span> <span data-ttu-id="92d6e-153">ただし、環境によっては、特定の脅威がここに示したのとは異なる度合いに相当すると提示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="92d6e-153">However, your environment or experience might suggest that a particular threat deserves a different rating than we have given it.</span></span> <span data-ttu-id="92d6e-154">すべてのセキュリティ シナリオと同様に、脅威レベルを判断するうえで最も信頼性が高いのは独自のデータです。サンプル シナリオでの分析と結果を参考にして独自の分析を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="92d6e-154">As with all security scenarios, your own data is the most robust to determine threat levels, and we recommend that you conduct your own analysis, using our analysis and results as a guide.</span></span>  
  
  <span data-ttu-id="92d6e-155">背景情報: データ フロー ダイアグラム (DFD) を除くの使用シナリオすべて同じです。</span><span class="sxs-lookup"><span data-stu-id="92d6e-155">The background information—except for the data flow diagram (DFD)—is the same for all our usage scenarios.</span></span> <span data-ttu-id="92d6e-156">次のセクションでは、各シナリオの DFD を示します。</span><span class="sxs-lookup"><span data-stu-id="92d6e-156">In the next sections we show the DFD for each scenario.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92d6e-157">参照</span><span class="sxs-lookup"><span data-stu-id="92d6e-157">See Also</span></span>  
 <span data-ttu-id="92d6e-158">[脅威モデル分析](../core/threat-model-analysis.md) </span><span class="sxs-lookup"><span data-stu-id="92d6e-158">[Threat Model Analysis](../core/threat-model-analysis.md) </span></span>  
 <span data-ttu-id="92d6e-159">[脅威モデル分析のサンプル シナリオ](../core/sample-scenarios-for-threat-model-analysis.md) </span><span class="sxs-lookup"><span data-stu-id="92d6e-159">[Sample Scenarios for Threat Model Analysis](../core/sample-scenarios-for-threat-model-analysis.md) </span></span>  
 <span data-ttu-id="92d6e-160">[セキュリティの計画](../core/planning-for-security.md) </span><span class="sxs-lookup"><span data-stu-id="92d6e-160">[Planning for Security](../core/planning-for-security.md) </span></span>  
 [<span data-ttu-id="92d6e-161">中小企業向けのサンプル アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="92d6e-161">Sample Architectures for Small & Medium-Sized Companies</span></span>](../core/sample-architectures-for-small-medium-sized-companies.md)