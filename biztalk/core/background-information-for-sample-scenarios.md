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
ms.openlocfilehash: b135dc4b322a2fe09289e971021ddbb387cf2915
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530645"
---
# <a name="background-information-for-sample-scenarios"></a><span data-ttu-id="d38cf-102">サンプル シナリオの背景情報</span><span class="sxs-lookup"><span data-stu-id="d38cf-102">Background Information for Sample Scenarios</span></span>
<span data-ttu-id="d38cf-103">このトピックでには、このセクションではシナリオの背景情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d38cf-103">This topic contains background information for the scenarios in this section.</span></span>  
  
## <a name="background-for-all-scenarios"></a><span data-ttu-id="d38cf-104">すべてのシナリオの背景</span><span class="sxs-lookup"><span data-stu-id="d38cf-104">Background for all scenarios</span></span>  
 <span data-ttu-id="d38cf-105">主要な脅威モデルは、会議、前に、次のような背景情報を収集しました。</span><span class="sxs-lookup"><span data-stu-id="d38cf-105">Before the main threat model meeting, we collected the following background information.</span></span> <span data-ttu-id="d38cf-106">この情報は、サンプル アーキテクチャで特定されたすべての使用シナリオに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d38cf-106">This information applies to all the usage scenarios we identified for the sample architecture:</span></span>  
  
-   <span data-ttu-id="d38cf-107">アーキテクチャの境界およびスコープ</span><span class="sxs-lookup"><span data-stu-id="d38cf-107">Boundaries and scope of the architecture</span></span>  
  
-   <span data-ttu-id="d38cf-108">信頼と信頼されていないコンポーネント間の境界</span><span class="sxs-lookup"><span data-stu-id="d38cf-108">Boundaries between trusted and untrusted components</span></span>  
  
-   <span data-ttu-id="d38cf-109">各コンポーネントの構成および管理モデル</span><span class="sxs-lookup"><span data-stu-id="d38cf-109">Configuration and administration model for each component</span></span>  
  
-   <span data-ttu-id="d38cf-110">その他のコンポーネントおよびアプリケーションに関する前提条件</span><span class="sxs-lookup"><span data-stu-id="d38cf-110">Assumptions about other components and applications</span></span>  
  
### <a name="boundaries-and-scope-of-the-architecture"></a><span data-ttu-id="d38cf-111">アーキテクチャの境界およびスコープ</span><span class="sxs-lookup"><span data-stu-id="d38cf-111">Boundaries and scope of the architecture</span></span>  
  
-   <span data-ttu-id="d38cf-112">ファイアウォール 2 保護サーバーとアプリケーション E ビジネス ドメインの境界ネットワークと (たとえば、企業ドメインまたはその他のアプリケーションのドメイン) 環境での他のドメインの両方。</span><span class="sxs-lookup"><span data-stu-id="d38cf-112">Firewall 2 helps protect the servers and applications in the E-Business domain both from the perimeter network and from any other domains in your environment (for example, a corporate domain or domains for other applications).</span></span>  
  
-   <span data-ttu-id="d38cf-113">2 つのルートを受信したすべてのファイアウォールおよび E ビジネス ドメインへのトラフィックを送信します。</span><span class="sxs-lookup"><span data-stu-id="d38cf-113">Firewall 2 routes all incoming and outgoing traffic to the E-Business domain.</span></span>  
  
-   <span data-ttu-id="d38cf-114">すべてのユーザー グループと BizTalk Server 環境にアクセスするアカウントには、E ビジネス ドメイン内のグローバル グループがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="d38cf-114">All user groups and accounts that access the BizTalk Server environment must be global groups in the E-Business domain.</span></span>  
  
-   <span data-ttu-id="d38cf-115">アクセスは、ホスト インスタンスのサービス アカウントに制限されていますすべてのアプリケーション ファイル、SQL、またはメッセージ キューは受信サーバーにメッセージをドロップします。BizTalk Server、エンタープライズ シングル サインオン (SSO)、および Windows 管理者とします。</span><span class="sxs-lookup"><span data-stu-id="d38cf-115">Access is limited to the service account for the host instance; any applications that drop messages in the receive server for File, SQL, or Message Queuing; and administrators for BizTalk Server, Enterprise Single Sign-On (SSO), and Windows.</span></span>  
  
### <a name="boundaries-between-trusted-and-untrusted-companies"></a><span data-ttu-id="d38cf-116">信頼と信頼されていない企業間の境界</span><span class="sxs-lookup"><span data-stu-id="d38cf-116">Boundaries between trusted and untrusted companies</span></span>  
  
-   <span data-ttu-id="d38cf-117">2 つのルートを受信したすべてのファイアウォールおよび E ビジネス ドメインへのトラフィックを送信します。</span><span class="sxs-lookup"><span data-stu-id="d38cf-117">Firewall 2 routes all incoming and outgoing traffic to the E-Business domain.</span></span>  
  
-   <span data-ttu-id="d38cf-118">BizTalk Server 内のアプリケーション間のセキュリティ境界としてさまざまな BizTalk ホストを使用します。</span><span class="sxs-lookup"><span data-stu-id="d38cf-118">Use different BizTalk Hosts as a security boundary between applications within BizTalk Server.</span></span>  
  
-   <span data-ttu-id="d38cf-119">アプリケーション (たとえば、サード パーティのコンポーネント信頼されたホストで実行しないで) 内でコードを信頼する場合にのみ、信頼されたホストを使用します。</span><span class="sxs-lookup"><span data-stu-id="d38cf-119">Use trusted hosts only when you trust the code within the application (for example, do not run third-party components in a trusted host).</span></span>  
  
### <a name="configuration-and-administration-model-for-each-component"></a><span data-ttu-id="d38cf-120">各コンポーネントの構成および管理モデル</span><span class="sxs-lookup"><span data-stu-id="d38cf-120">Configuration and administration model for each component</span></span>  
 <span data-ttu-id="d38cf-121">**構成モデル:**</span><span class="sxs-lookup"><span data-stu-id="d38cf-121">**Configuration model:**</span></span>  
  
- <span data-ttu-id="d38cf-122">BizTalk Server ランタイム コンポーネントは、BizTalk サーバーでのみインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d38cf-122">BizTalk Server runtime components are installed only on the BizTalk Servers.</span></span>  
  
- <span data-ttu-id="d38cf-123">マスター シークレット サーバーには、追加のコンポーネントがありません。</span><span class="sxs-lookup"><span data-stu-id="d38cf-123">Master secret server has no additional components.</span></span>  
  
- <span data-ttu-id="d38cf-124">SQL Server には、すべての BizTalk Server データベースが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d38cf-124">SQL Server contains all BizTalk Server databases.</span></span>  
  
- <span data-ttu-id="d38cf-125">境界ネットワーク内のサーバーには、BizTalk Server コンポーネントがありません。</span><span class="sxs-lookup"><span data-stu-id="d38cf-125">Servers in the perimeter networks do not have any BizTalk Server components.</span></span>  
  
- <span data-ttu-id="d38cf-126">管理クライアントを使用して、E ビジネス ドメインのすべてのサーバーを管理します。</span><span class="sxs-lookup"><span data-stu-id="d38cf-126">Administration client is used to administer all servers in the E-Business domain.</span></span>  
  
  <span data-ttu-id="d38cf-127">**管理モデル:**</span><span class="sxs-lookup"><span data-stu-id="d38cf-127">**Administration model:**</span></span>  
  
- <span data-ttu-id="d38cf-128">デスクトップ (またはラップトップ) からは、管理者は、(ターミナル サービスまたはリモート デスクトップ接続を使用して) 管理ツールを使用したコンピューターに接続します。</span><span class="sxs-lookup"><span data-stu-id="d38cf-128">From a desktop (or laptop), an administrator connects to the computer that has the administration tools (using either Terminal Services or Remote Desktop connection).</span></span> <span data-ttu-id="d38cf-129">ツールが管理されているコンピューターに接続すると、管理者後、管理者は、すべてのサーバーとドメイン内のアプリケーションを管理するのに、BizTalk 管理ツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d38cf-129">After the administrator connects to the computer that has the administration tools, the administrator can use the BizTalk Administration tools to manage all servers and applications within the domain.</span></span>  
  
### <a name="assumptions-about-other-components-and-applications"></a><span data-ttu-id="d38cf-130">その他のコンポーネントおよびアプリケーションに関する前提条件</span><span class="sxs-lookup"><span data-stu-id="d38cf-130">Assumptions about other components and applications</span></span>  
 <span data-ttu-id="d38cf-131">その他のすべてのアプリケーションおよび BizTalk Server 環境と対話するコンポーネント (たとえば、境界ネットワーク) で、E ビジネス ドメイン以外では。</span><span class="sxs-lookup"><span data-stu-id="d38cf-131">All other applications and components that interact with the BizTalk Server environment are in a domain other than the E-Business domain (for example, in a perimeter network).</span></span> <span data-ttu-id="d38cf-132">これらのアプリケーションとコンポーネント、および BizTalk Server 環境からのトラフィックは、ファイアウォール 2 経由で移動します。</span><span class="sxs-lookup"><span data-stu-id="d38cf-132">The traffic from those applications and components to and from the BizTalk Server environment goes through Firewall 2.</span></span>  
  
 <span data-ttu-id="d38cf-133">BizTalk Server のすべてのサード パーティ製アプリケーションは、信頼できるベンダーから取得されます。</span><span class="sxs-lookup"><span data-stu-id="d38cf-133">Any third-party applications for BizTalk Server come from a trusted vendor.</span></span>  
  
### <a name="data-flow-diagrams"></a><span data-ttu-id="d38cf-134">データ フロー ダイアグラム</span><span class="sxs-lookup"><span data-stu-id="d38cf-134">Data flow diagrams</span></span>  
 <span data-ttu-id="d38cf-135">各使用シナリオの背景情報の最後の要素は、データ フロー ダイアグラム (DFD) です。</span><span class="sxs-lookup"><span data-stu-id="d38cf-135">The final element of background information for each usage scenario is a data flow diagram (DFD).</span></span> <span data-ttu-id="d38cf-136">DFD は、アーキテクチャを介したデータの流れを示しています。</span><span class="sxs-lookup"><span data-stu-id="d38cf-136">A DFD illustrates how data flows through the architecture.</span></span> <span data-ttu-id="d38cf-137">各シナリオでは、個別の DFD が。</span><span class="sxs-lookup"><span data-stu-id="d38cf-137">Each scenario has a different DFD.</span></span> <span data-ttu-id="d38cf-138">このドキュメントでは、データ フローの図は、次の図に示すように要素を含めます。</span><span class="sxs-lookup"><span data-stu-id="d38cf-138">In this document, the data flow diagrams contain the elements shown in the following figure.</span></span>  
  
 <span data-ttu-id="d38cf-139">**図 1 DFD の要素**</span><span class="sxs-lookup"><span data-stu-id="d38cf-139">**Figure 1 Elements of the DFD**</span></span>  
  
 <span data-ttu-id="d38cf-140">![DFD の要素](../core/media/tdi-sec-dfd-legend.gif "TDI_Sec_DFD_Legend")</span><span class="sxs-lookup"><span data-stu-id="d38cf-140">![Elements of the DFD](../core/media/tdi-sec-dfd-legend.gif "TDI_Sec_DFD_Legend")</span></span>  
  
## <a name="background-for-adapter-scenarios"></a><span data-ttu-id="d38cf-141">アダプタ シナリオの背景</span><span class="sxs-lookup"><span data-stu-id="d38cf-141">Background for adapter scenarios</span></span>  
 <span data-ttu-id="d38cf-142">次に基づいた使用シナリオがわかりました、サンプル アーキテクチャでは、アダプターの一部では、ボックスを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="d38cf-142">In our sample architecture, we identified the following usage scenarios based on some of the adapters you can use out-of-the-box:</span></span>  
  
- <span data-ttu-id="d38cf-143">HTTP アダプタと SOAP (Web サービス) アダプタ シナリオ</span><span class="sxs-lookup"><span data-stu-id="d38cf-143">HTTP and SOAP (Web services) adapters scenario</span></span>  
  
- <span data-ttu-id="d38cf-144">BizTalk メッセージ キュー アダプタ シナリオ</span><span class="sxs-lookup"><span data-stu-id="d38cf-144">BizTalk Message Queuing adapter scenario</span></span>  
  
- <span data-ttu-id="d38cf-145">ファイル アダプタ シナリオ</span><span class="sxs-lookup"><span data-stu-id="d38cf-145">File adapter scenario</span></span>  
  
- <span data-ttu-id="d38cf-146">FTP アダプタ シナリオ</span><span class="sxs-lookup"><span data-stu-id="d38cf-146">FTP adapter scenario</span></span>  
  
  <span data-ttu-id="d38cf-147">各シナリオでは、脅威モデル分析を完了する手順に従いました。</span><span class="sxs-lookup"><span data-stu-id="d38cf-147">For each scenario, we followed these steps to complete the threat model analysis:</span></span>  
  
- <span data-ttu-id="d38cf-148">背景情報の収集</span><span class="sxs-lookup"><span data-stu-id="d38cf-148">Collect background information</span></span>  
  
- <span data-ttu-id="d38cf-149">脅威モデルの作成と分析</span><span class="sxs-lookup"><span data-stu-id="d38cf-149">Create and analyze the threat model</span></span>  
  
- <span data-ttu-id="d38cf-150">脅威の確認</span><span class="sxs-lookup"><span data-stu-id="d38cf-150">Review threats</span></span>  
  
- <span data-ttu-id="d38cf-151">緩和方法とテクノロジの特定</span><span class="sxs-lookup"><span data-stu-id="d38cf-151">Identify mitigation techniques and technologies</span></span>  
  
  <span data-ttu-id="d38cf-152">各シナリオでは、さまざまな攻撃を表すことが脅威のレベルの一般的な評価の作成を試みました。</span><span class="sxs-lookup"><span data-stu-id="d38cf-152">For each scenario, we have tried to develop generic ratings of the level of threat that the various attacks might represent.</span></span> <span data-ttu-id="d38cf-153">ただし、環境が、ある特定の脅威は異なる度合いによりもお勧めします可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d38cf-153">However, your environment or experience might suggest that a particular threat deserves a different rating than we have given it.</span></span> <span data-ttu-id="d38cf-154">すべてのセキュリティ シナリオでは、独自のデータは最も堅牢な脅威レベルを判断すると、ことをお勧めをガイドとして、分析と結果を使用して、独自の分析が実施します。</span><span class="sxs-lookup"><span data-stu-id="d38cf-154">As with all security scenarios, your own data is the most robust to determine threat levels, and we recommend that you conduct your own analysis, using our analysis and results as a guide.</span></span>  
  
  <span data-ttu-id="d38cf-155">背景情報: データ フロー ダイアグラム (DFD) を除くの使用シナリオすべて同じです。</span><span class="sxs-lookup"><span data-stu-id="d38cf-155">The background information—except for the data flow diagram (DFD)—is the same for all our usage scenarios.</span></span> <span data-ttu-id="d38cf-156">次のセクションでは、各シナリオの DFD を示しています。</span><span class="sxs-lookup"><span data-stu-id="d38cf-156">In the next sections we show the DFD for each scenario.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d38cf-157">参照</span><span class="sxs-lookup"><span data-stu-id="d38cf-157">See Also</span></span>  
 <span data-ttu-id="d38cf-158">[脅威モデル分析](../core/threat-model-analysis.md) </span><span class="sxs-lookup"><span data-stu-id="d38cf-158">[Threat Model Analysis](../core/threat-model-analysis.md) </span></span>  
 <span data-ttu-id="d38cf-159">[脅威モデル分析のサンプル シナリオ](../core/sample-scenarios-for-threat-model-analysis.md) </span><span class="sxs-lookup"><span data-stu-id="d38cf-159">[Sample Scenarios for Threat Model Analysis](../core/sample-scenarios-for-threat-model-analysis.md) </span></span>  
 <span data-ttu-id="d38cf-160">[セキュリティの計画](../core/planning-for-security.md) </span><span class="sxs-lookup"><span data-stu-id="d38cf-160">[Planning for Security](../core/planning-for-security.md) </span></span>  
 [<span data-ttu-id="d38cf-161">中小企業向けのサンプル アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="d38cf-161">Sample Architectures for Small & Medium-Sized Companies</span></span>](../core/sample-architectures-for-small-medium-sized-companies.md)