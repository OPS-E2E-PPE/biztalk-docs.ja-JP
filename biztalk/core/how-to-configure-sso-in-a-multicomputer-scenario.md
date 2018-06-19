---
title: 複数コンピューター環境のシナリオで SSO を構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, SSO
- SSO database, clustering
- clustering, Master Secret server
- SSO, configuring
- configuring, Master Secret server
- Master Secret server, clustering
- clustering, SSO database
- Master Secret server, configuring
- SSO, multiple computers
ms.assetid: 4511a03d-96f2-45f0-9891-e8b3e253499c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45bfa58c1fc11a76109f56938b8e1b43790935f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248754"
---
# <a name="how-to-configure-sso-in-a-multicomputer-scenario"></a><span data-ttu-id="de93f-102">複数コンピューター環境のシナリオで SSO を構成する方法</span><span class="sxs-lookup"><span data-stu-id="de93f-102">How to Configure SSO in a Multicomputer Scenario</span></span>
<span data-ttu-id="de93f-103">このセクションでは、3 台のコンピュータが存在するシナリオで、エンタープライズ シングル サインオン (SSO) を構成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="de93f-103">This section contains instructions for configuring Enterprise Single Sign-On (SSO) in a three-computer scenario.</span></span>  
  
 <span data-ttu-id="de93f-104">次のシナリオでは、コンピュータ A がマスタ シークレット サーバー、コンピュータ B がシングル サインオン サーバーです。コンピュータ C には SSO データベースが保持されています。</span><span class="sxs-lookup"><span data-stu-id="de93f-104">In the following scenario, computer A is the master secret server, computer B is the Single Sign-On server, and computer C holds the SSO database.</span></span> <span data-ttu-id="de93f-105">コンピュータ B は、ランタイム サーバー、管理サーバー (SSO の管理サブサービスにより、SSO データベースを管理するために使用されるサーバー)、またはマッピング サーバー (SSO の管理サブサービスおよびクライアント サブサービスにより、マッピングを管理するために使用されるサーバー) として機能します。</span><span class="sxs-lookup"><span data-stu-id="de93f-105">Computer B can act as a runtime server, as an administration server (administration sub services of SSO use this server for managing the SSO database), or as a mapping server (administration and client sub services of SSO use this server to manage mappings).</span></span>  
  
 <span data-ttu-id="de93f-106">環境内の SSO サーバーの台数を増やす場合は、コンピュータ B を構成する手順に従ってください。新しい SSO サーバーは、既存の SSO データベースを参照します。マスタ シークレット サーバーにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="de93f-106">If you want to add more SSO servers to your environment, follow the steps for configuring computer B. Any new SSO servers will point to the existing SSO database, and cannot be the master secret server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="de93f-107">マスタ シークレット サーバーは、シングル サインオン サーバーおよび SSO データベースとは別のコンピュータで構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="de93f-107">It is recommended that you configure the master secret server on a different computer from the Single Sign-On server and the SSO database.</span></span>  
  
### <a name="to-configure-the-master-secret-server-and-create-the-sso-database-on-computer-a"></a><span data-ttu-id="de93f-108">コンピュータ A でマスタ シークレット サーバーを構成して SSO データベースを作成するには</span><span class="sxs-lookup"><span data-stu-id="de93f-108">To configure the master secret server and create the SSO database on Computer A</span></span>  
  
1.  <span data-ttu-id="de93f-109">BizTalk Server のカスタム インストールを実行し、エンタープライズ シングル サインオンのマスタ シークレット サーバー コンポーネントのみをインストールします。</span><span class="sxs-lookup"><span data-stu-id="de93f-109">Perform a custom installation of BizTalk Server, and install only the Enterprise Single Sign-On Master Secret Server component.</span></span>  
  
2.  <span data-ttu-id="de93f-110">構成ウィザードを実行し、マスタ シークレット サーバーで SSO を構成します。</span><span class="sxs-lookup"><span data-stu-id="de93f-110">Run the Configuration Wizard to configure SSO on the master secret server.</span></span> <span data-ttu-id="de93f-111">**構成についての質問**するオプションを選択 ページで、**新しい SSO システムを作成する**です。</span><span class="sxs-lookup"><span data-stu-id="de93f-111">On the **Configuration Questions** page, select the option to **Create a new SSO system**.</span></span>  
  
3.  <span data-ttu-id="de93f-112">**Windows アカウント** ページで、SSO サービスのサービス アカウントの資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="de93f-112">On the **Windows Accounts** page, specify the service account credentials for the SSO service.</span></span> <span data-ttu-id="de93f-113">このアカウントは、SSO 管理者グループのメンバである必要があります。</span><span class="sxs-lookup"><span data-stu-id="de93f-113">This must be a member of the SSO Administrators group.</span></span>  
  
4.  <span data-ttu-id="de93f-114">**データベース構成** ページで、SQL Server (コンピュータ C) の場所と SSO データベース (SSODB) の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="de93f-114">On the **Database Configurations** page, specify the location of the SQL Server (computer C) and the name of the SSO database (SSODB).</span></span>  
  
5.  <span data-ttu-id="de93f-115">マスタ シークレットをバックアップするオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="de93f-115">Specify the options to back up the Master Secret.</span></span>  
  
6.  <span data-ttu-id="de93f-116">構成を完了します。</span><span class="sxs-lookup"><span data-stu-id="de93f-116">Complete the configuration.</span></span>  
  
### <a name="to-configure-the-sso-server-on-computer-b"></a><span data-ttu-id="de93f-117">コンピュータ B で SSO サーバーを構成するには</span><span class="sxs-lookup"><span data-stu-id="de93f-117">To configure the SSO server on Computer B</span></span>  
  
1.  <span data-ttu-id="de93f-118">コンピュータ B にエンタープライズ シングル サインオンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="de93f-118">Install Enterprise Single Sign-On on Computer B.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="de93f-119">このコンピュータは、BizTalk Server コンピュータか Host Integration Server コンピュータ、Web サーバー、または SSO のみのサーバー (SSO ランタイム コンポーネント) にすることができます。</span><span class="sxs-lookup"><span data-stu-id="de93f-119">This can be a BizTalk Server or Host Integration Server computer, a Web server, or an SSO-only server (SSO runtime components).</span></span>  
  
2.  <span data-ttu-id="de93f-120">構成ウィザードを実行して、SSO を構成します。</span><span class="sxs-lookup"><span data-stu-id="de93f-120">Run the Configuration Wizard to configure SSO.</span></span> <span data-ttu-id="de93f-121">**構成についての質問**するオプションを選択 ページで、**既存の SSO システムに参加**です。</span><span class="sxs-lookup"><span data-stu-id="de93f-121">On the **Configuration Questions** page, select the option to **Join an existing SSO system**.</span></span>  
  
3.  <span data-ttu-id="de93f-122">**Windows アカウント** ページで、SSO サービスのサービス アカウントの資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="de93f-122">On the **Windows Accounts** page, specify the service account credentials for the SSO service.</span></span> <span data-ttu-id="de93f-123">このアカウントは、SSO 管理者グループのメンバである必要があります。</span><span class="sxs-lookup"><span data-stu-id="de93f-123">This must be a member of the SSO Administrators group.</span></span>  
  
4.  <span data-ttu-id="de93f-124">**データベース構成** ページで、SQL Server (コンピュータ C) の場所と SSO データベース (SSODB) の名前をポイントします。</span><span class="sxs-lookup"><span data-stu-id="de93f-124">On the **Database Configurations** page, point to the location of the SQL Server (computer C) and the name of the SSO database (SSODB).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de93f-125">参照</span><span class="sxs-lookup"><span data-stu-id="de93f-125">See Also</span></span>  
 <span data-ttu-id="de93f-126">[マスター シークレット サーバーをクラスター化する方法](../core/how-to-cluster-the-master-secret-server1.md) </span><span class="sxs-lookup"><span data-stu-id="de93f-126">[How to Cluster the Master Secret Server](../core/how-to-cluster-the-master-secret-server1.md) </span></span>  
 [<span data-ttu-id="de93f-127">SSO のインストール</span><span class="sxs-lookup"><span data-stu-id="de93f-127">Installing SSO</span></span>](../core/installing-sso.md)