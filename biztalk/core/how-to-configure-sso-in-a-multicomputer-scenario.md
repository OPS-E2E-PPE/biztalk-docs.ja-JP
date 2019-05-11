---
title: 複数コンピューターのシナリオで SSO を構成する方法 |Microsoft Docs
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
ms.openlocfilehash: 09bdaefef80a0a3e975c9d63e1844475ae698c4d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386211"
---
# <a name="how-to-configure-sso-in-a-multicomputer-scenario"></a><span data-ttu-id="633de-102">複数コンピューターのシナリオで SSO を構成する方法</span><span class="sxs-lookup"><span data-stu-id="633de-102">How to Configure SSO in a Multicomputer Scenario</span></span>
<span data-ttu-id="633de-103">このセクションでは、3 台のコンピューターのシナリオでは、エンタープライズ シングル サインオン (SSO) を構成するための手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="633de-103">This section contains instructions for configuring Enterprise Single Sign-On (SSO) in a three-computer scenario.</span></span>  
  
 <span data-ttu-id="633de-104">次のシナリオでは、コンピュータ A がマスタ シークレット サーバー、コンピュータ B が、シングル サインオン サーバーおよびコンピューター C は、SSO データベースを保持します。</span><span class="sxs-lookup"><span data-stu-id="633de-104">In the following scenario, computer A is the master secret server, computer B is the Single Sign-On server, and computer C holds the SSO database.</span></span> <span data-ttu-id="633de-105">コンピューター B の管理サーバーとしてのランタイム サーバーとして動作することができます (SSO の管理サブサービスを使用して、このサーバーの SSO データベースを管理するため)、またはマッピング サーバー (管理およびクライアント サブサービスの SSO のマッピングの管理にこのサーバーを使用)。</span><span class="sxs-lookup"><span data-stu-id="633de-105">Computer B can act as a runtime server, as an administration server (administration sub services of SSO use this server for managing the SSO database), or as a mapping server (administration and client sub services of SSO use this server to manage mappings).</span></span>  
  
 <span data-ttu-id="633de-106">環境内に SSO サーバーを追加する場合はコンピューター B を構成する手順に従ってください。新しい SSO サーバーは、既存の SSO データベースがポイントして、マスター シークレット サーバーにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="633de-106">If you want to add more SSO servers to your environment, follow the steps for configuring computer B. Any new SSO servers will point to the existing SSO database, and cannot be the master secret server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="633de-107">シングル サインオン サーバーおよび SSO データベースから別のコンピューターでは、マスター シークレット サーバーを構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="633de-107">It is recommended that you configure the master secret server on a different computer from the Single Sign-On server and the SSO database.</span></span>  
  
### <a name="to-configure-the-master-secret-server-and-create-the-sso-database-on-computer-a"></a><span data-ttu-id="633de-108">マスター シークレット サーバーを構成し、コンピューター A で、SSO データベースを作成するには</span><span class="sxs-lookup"><span data-stu-id="633de-108">To configure the master secret server and create the SSO database on Computer A</span></span>  
  
1.  <span data-ttu-id="633de-109">BizTalk Server のカスタム インストールを実行し、エンタープライズ シングル サインオン マスター シークレット サーバー コンポーネントのみをインストールします。</span><span class="sxs-lookup"><span data-stu-id="633de-109">Perform a custom installation of BizTalk Server, and install only the Enterprise Single Sign-On Master Secret Server component.</span></span>  
  
2.  <span data-ttu-id="633de-110">SSO マスター シークレット サーバーを構成する構成ウィザードを実行します。</span><span class="sxs-lookup"><span data-stu-id="633de-110">Run the Configuration Wizard to configure SSO on the master secret server.</span></span> <span data-ttu-id="633de-111">**構成についての質問**するオプションを選択 ページで、**新しい SSO システムを作成する**します。</span><span class="sxs-lookup"><span data-stu-id="633de-111">On the **Configuration Questions** page, select the option to **Create a new SSO system**.</span></span>  
  
3.  <span data-ttu-id="633de-112">**Windows アカウント**ページで、SSO サービスのサービス アカウントの資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="633de-112">On the **Windows Accounts** page, specify the service account credentials for the SSO service.</span></span> <span data-ttu-id="633de-113">これにより、SSO 管理者グループのメンバーがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="633de-113">This must be a member of the SSO Administrators group.</span></span>  
  
4.  <span data-ttu-id="633de-114">**データベース構成** ページで、SQL Server (コンピュータ C) の場所と SSO データベース (SSODB) の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="633de-114">On the **Database Configurations** page, specify the location of the SQL Server (computer C) and the name of the SSO database (SSODB).</span></span>  
  
5.  <span data-ttu-id="633de-115">マスター シークレットをバックアップするオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="633de-115">Specify the options to back up the Master Secret.</span></span>  
  
6.  <span data-ttu-id="633de-116">構成を完了します。</span><span class="sxs-lookup"><span data-stu-id="633de-116">Complete the configuration.</span></span>  
  
### <a name="to-configure-the-sso-server-on-computer-b"></a><span data-ttu-id="633de-117">コンピューター B で SSO サーバーを構成するには</span><span class="sxs-lookup"><span data-stu-id="633de-117">To configure the SSO server on Computer B</span></span>  
  
1.  <span data-ttu-id="633de-118">コンピューター B にエンタープライズ シングル サインオンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="633de-118">Install Enterprise Single Sign-On on Computer B.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="633de-119">BizTalk Server または Host Integration Server コンピューター、Web サーバー、または SSO のみサーバー (SSO ランタイム コンポーネント) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="633de-119">This can be a BizTalk Server or Host Integration Server computer, a Web server, or an SSO-only server (SSO runtime components).</span></span>  
  
2.  <span data-ttu-id="633de-120">SSO を構成する構成ウィザードを実行します。</span><span class="sxs-lookup"><span data-stu-id="633de-120">Run the Configuration Wizard to configure SSO.</span></span> <span data-ttu-id="633de-121">**構成についての質問**するオプションを選択 ページで、**既存の SSO システムに参加**します。</span><span class="sxs-lookup"><span data-stu-id="633de-121">On the **Configuration Questions** page, select the option to **Join an existing SSO system**.</span></span>  
  
3.  <span data-ttu-id="633de-122">**Windows アカウント**ページで、SSO サービスのサービス アカウントの資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="633de-122">On the **Windows Accounts** page, specify the service account credentials for the SSO service.</span></span> <span data-ttu-id="633de-123">これにより、SSO 管理者グループのメンバーがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="633de-123">This must be a member of the SSO Administrators group.</span></span>  
  
4.  <span data-ttu-id="633de-124">**データベース構成** ページで、SQL Server (コンピュータ C) の場所と SSO データベース (SSODB) の名前をポイントします。</span><span class="sxs-lookup"><span data-stu-id="633de-124">On the **Database Configurations** page, point to the location of the SQL Server (computer C) and the name of the SSO database (SSODB).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="633de-125">参照</span><span class="sxs-lookup"><span data-stu-id="633de-125">See Also</span></span>  
 <span data-ttu-id="633de-126">[マスター シークレット サーバーをクラスター化する方法](../core/how-to-cluster-the-master-secret-server1.md) </span><span class="sxs-lookup"><span data-stu-id="633de-126">[How to Cluster the Master Secret Server](../core/how-to-cluster-the-master-secret-server1.md) </span></span>  
 [<span data-ttu-id="633de-127">SSO のインストール</span><span class="sxs-lookup"><span data-stu-id="633de-127">Installing SSO</span></span>](../core/installing-sso.md)