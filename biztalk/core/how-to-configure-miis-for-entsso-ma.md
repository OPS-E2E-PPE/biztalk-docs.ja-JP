---
title: ENTSSO MA 用に MIIS を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7820384-ff64-4628-9e35-02b13803928f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e536e44ec6c76ba3bf44b346fd6b44e54c3f05b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341295"
---
# <a name="how-to-configure-miis-for-entsso-ma"></a><span data-ttu-id="86dcc-102">ENTSSO MA 用に MIIS を構成する方法</span><span class="sxs-lookup"><span data-stu-id="86dcc-102">How to Configure MIIS for ENTSSO MA</span></span>
<span data-ttu-id="86dcc-103">Microsoft Identity Integration Server (MIIS) を実行するコンピューターでエンタープライズ シングル サインオン (SSO) 管理機能 (完全なバージョンまたは管理ツールのみのバージョン) をインストールするときに、ENTSSO 管理エージェントは自動的にインストールします。</span><span class="sxs-lookup"><span data-stu-id="86dcc-103">When you install the Enterprise Single Sign-On (SSO) Administration feature (either the full version or the Admin-only version) on a computer running Microsoft Identity Integration Server (MIIS), the ENTSSO Management Agent is automatically installed.</span></span> <span data-ttu-id="86dcc-104">つまり、MIIS を起動するときにほぼすべての構成が既に実行されています。</span><span class="sxs-lookup"><span data-stu-id="86dcc-104">This means that when you open MIIS, nearly all of the configuration has already been done.</span></span> <span data-ttu-id="86dcc-105">接続情報は、一部が不足しているだけです。</span><span class="sxs-lookup"><span data-stu-id="86dcc-105">The only part missing is the connection information.</span></span>  
  
 <span data-ttu-id="86dcc-106">この手順を開始する前に、次の情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="86dcc-106">Before starting this procedure, make sure you have the following information available:</span></span>  
  
-   <span data-ttu-id="86dcc-107">ENTSSO サーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="86dcc-107">ENTSSO Server name.</span></span>  
  
-   <span data-ttu-id="86dcc-108">ユーザー Id とする ENTSSO 管理エージェントは、SSO サーバーと通信する Windows アカウントのパスワード。</span><span class="sxs-lookup"><span data-stu-id="86dcc-108">UserId and password of the Windows account under which the ENTSSO Management Agent will communicate with the SSO Server.</span></span>  
  
### <a name="to-configure-the-management-agent-within-miis"></a><span data-ttu-id="86dcc-109">MIIS で管理エージェントを構成するには</span><span class="sxs-lookup"><span data-stu-id="86dcc-109">To configure the Management Agent within MIIS</span></span>  
  
1.  <span data-ttu-id="86dcc-110">MIIS を開き、開く、 **Identity Manager**します。</span><span class="sxs-lookup"><span data-stu-id="86dcc-110">Open MIIS, and open the **Identity Manager**.</span></span>  
  
2.  <span data-ttu-id="86dcc-111">開く、**管理エージェントを作成** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="86dcc-111">Open the **Create Management Agent** dialog box.</span></span>  
  
3.  <span data-ttu-id="86dcc-112">選択**エンタープライズ シングル サインオン**一覧にします。</span><span class="sxs-lookup"><span data-stu-id="86dcc-112">Select **Enterprise Single Sign-On** in the list.</span></span>  
  
     <span data-ttu-id="86dcc-113">起動、**管理エージェント作成ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="86dcc-113">This starts the **Create Management Agent Wizard**.</span></span>  
  
4.  <span data-ttu-id="86dcc-114">**接続情報の構成**ページで、**接続先:** フィールドに、SSO サーバーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="86dcc-114">On the **Configure Connection Information** page, in the **Connect To:** field, enter the name of the SSO Server.</span></span>  
  
5.  <span data-ttu-id="86dcc-115">ENTSSO 管理エージェントの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="86dcc-115">Enter the name of the ENTSSO Management Agent.</span></span> <span data-ttu-id="86dcc-116">この名前は、ENTSSO.xml ファイルで指定された名前と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="86dcc-116">This name must match the name specified in your ENTSSO.xml file.</span></span>  
  
6.  <span data-ttu-id="86dcc-117">**ユーザー**フィールドに、ENTSSO 管理エージェントを使用して、SSO データベース内のマッピングを管理するドメイン アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="86dcc-117">In the **User** field, specify the domain account that the ENTSSO Management Agent uses to manage mappings in the SSO Database.</span></span>  
  
     <span data-ttu-id="86dcc-118">このアカウントは、いずれか、SSO システム内の SSO 関連管理者または SSO 管理者アカウントのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="86dcc-118">This account should be either a member of the SSO Affiliate Administrators or SSO Administrators accounts within the SSO System.</span></span>  
  
7.  <span data-ttu-id="86dcc-119">**パスワード**フィールドに、そのユーザーのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="86dcc-119">In the **Password** field, enter the password for that user.</span></span>  
  
8.  <span data-ttu-id="86dcc-120">をクリックして**次**、既定値のままに到達するまで、**拡張機能の構成**ページ。</span><span class="sxs-lookup"><span data-stu-id="86dcc-120">Click **Next**, accepting the defaults until you reach the **Configure Extensions** page.</span></span>  
  
9. <span data-ttu-id="86dcc-121">ほぼ**接続情報**パスワード拡張機能をクリックして**設定**します。</span><span class="sxs-lookup"><span data-stu-id="86dcc-121">Near **Connection information** for password extension, click **Settings**.</span></span>  
  
     <span data-ttu-id="86dcc-122">**接続設定** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="86dcc-122">The **Connection Settings** dialog box appears.</span></span>  
  
10. <span data-ttu-id="86dcc-123">**接続先**ボックスに、適切なアカウントを入力します。</span><span class="sxs-lookup"><span data-stu-id="86dcc-123">In the **Connect To** box, enter the appropriate account.</span></span> <span data-ttu-id="86dcc-124">このアカウントは、指定されたコンピューターで実行されている ENTSSO サービスのサービス アカウントと同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="86dcc-124">This account must be the same as the service account for the ENTSSO service running on the computer specified.</span></span>  
  
11. <span data-ttu-id="86dcc-125">**ユーザー**と**パスワード**フィールドに、アカウントのユーザー名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="86dcc-125">In the **User** and **Password** fields, enter the user name and password for the account.</span></span>  
  
12. <span data-ttu-id="86dcc-126">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="86dcc-126">Click **OK**.</span></span>  
  
13. <span data-ttu-id="86dcc-127">**MIISCreate 管理エージェント**、 をクリックして**完了**します。</span><span class="sxs-lookup"><span data-stu-id="86dcc-127">In the **MIISCreate Management Agent**, click **Finish**.</span></span>  
  
14. <span data-ttu-id="86dcc-128">**Identity Manager**、クリックして、**ツール** メニューをクリック**オプション**します。</span><span class="sxs-lookup"><span data-stu-id="86dcc-128">While still in the **Identity Manager**, click the **Tools** menu, and then click **Options**.</span></span>  
  
     <span data-ttu-id="86dcc-129">**オプション** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="86dcc-129">The **Options** dialog box appears.</span></span>  
  
15. <span data-ttu-id="86dcc-130">選択**メタバース ルールの拡張機能を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="86dcc-130">Select **Enable metaverse rules extension**.</span></span>  
  
16. <span data-ttu-id="86dcc-131">**ルール拡張機能の名前フィールド**、入力**Microsoft.EnterpriseSingleSignOn.ManagementAgent.dll**します。</span><span class="sxs-lookup"><span data-stu-id="86dcc-131">In the **Rules extension name field**, enter **Microsoft.EnterpriseSingleSignOn.ManagementAgent.dll**.</span></span>  
  
17. <span data-ttu-id="86dcc-132">クリックして**OK** MIIS を閉じます。</span><span class="sxs-lookup"><span data-stu-id="86dcc-132">Click **OK** and close MIIS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86dcc-133">参照</span><span class="sxs-lookup"><span data-stu-id="86dcc-133">See Also</span></span>  
 [<span data-ttu-id="86dcc-134">ENTSSO 管理エージェントを使用する方法</span><span class="sxs-lookup"><span data-stu-id="86dcc-134">How to Use the ENTSSO Management Agent</span></span>](../core/how-to-use-the-entsso-management-agent.md)