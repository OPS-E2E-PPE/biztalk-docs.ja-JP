---
title: "SSO を監査する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [SSO], auditing
- SSO, auditing
- auditing [SSO]
- SSO database, auditing
ms.assetid: dc6d0726-fc31-4af2-9a23-8df9e3fc5836
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27528cf6da53c69db4b2bc6c9e1d296472b24186
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-audit-sso"></a><span data-ttu-id="cabcf-102">SSO を監査する方法</span><span class="sxs-lookup"><span data-stu-id="cabcf-102">How to Audit SSO</span></span>
<span data-ttu-id="cabcf-103">MMC スナップインまたはコマンド ラインを使用して、成功と失敗の監査のレベルを設定できます。</span><span class="sxs-lookup"><span data-stu-id="cabcf-103">You can use the MMC Snap-In or the command line to set both the positive and negative auditing levels.</span></span> <span data-ttu-id="cabcf-104">監査の結果は、イベント ログと、データベースの監査ログの両方に保存されます。</span><span class="sxs-lookup"><span data-stu-id="cabcf-104">Results of the auditing are stored in both the event logs and the audit logs of the database.</span></span>  
  
 <span data-ttu-id="cabcf-105">SSO 管理者は、企業の規定に応じて、成功と失敗の監査レベルを設定できます。</span><span class="sxs-lookup"><span data-stu-id="cabcf-105">SSO administrators can set the positive and negative audit levels that suit their corporate policies.</span></span> <span data-ttu-id="cabcf-106">成功と失敗の監査は、次のレベルのいずれかに設定できます。</span><span class="sxs-lookup"><span data-stu-id="cabcf-106">You can set positive and negative audits to one of the following levels:</span></span>  
  
 <span data-ttu-id="cabcf-107">0 = なし</span><span class="sxs-lookup"><span data-stu-id="cabcf-107">0 = None</span></span>  
  
 <span data-ttu-id="cabcf-108">1 = 低。</span><span class="sxs-lookup"><span data-stu-id="cabcf-108">1 = Low</span></span>  
  
 <span data-ttu-id="cabcf-109">2 = 中。</span><span class="sxs-lookup"><span data-stu-id="cabcf-109">2 = Medium</span></span>  
  
 <span data-ttu-id="cabcf-110">3 = 高。</span><span class="sxs-lookup"><span data-stu-id="cabcf-110">3 = High.</span></span> <span data-ttu-id="cabcf-111">このレベルは、ように、できるだけ多くの監査メッセージを発行します。</span><span class="sxs-lookup"><span data-stu-id="cabcf-111">This level issues as many audit messages as possible.</span></span>  
  
 <span data-ttu-id="cabcf-112">成功の監査の既定値は 0 (なし)、および失敗の監査の既定値は 1(low) します。</span><span class="sxs-lookup"><span data-stu-id="cabcf-112">The default value for positive auditing is 0 (none), and the default value for negative auditing is 1(low).</span></span>  
  
 <span data-ttu-id="cabcf-113">データベース レベルの監査を変更するには、XML ファイルを使用して SSO データベースを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cabcf-113">To change the database level auditing, you must update the SSO database using an XML file.</span></span> <span data-ttu-id="cabcf-114">SSO データベースを更新するためのサンプル XML ファイルは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cabcf-114">A sample XML file for updating the SSO database is:</span></span>  
  
```  
<sso>  
<globalnfo>  
<auditDeletedApps>1000</auditDeletedApps>  
<auditDeletedMappings>1000</auditDeletedMappings>  
<auditCredentialLookups>1000</auditCredentialLookups>  
</globalInfo>  
</sso>  
  
```  
  
### <a name="to-audit-single-sign-on-using-the-mmc-snap-in"></a><span data-ttu-id="cabcf-115">MMC スナップインでシングル サインオンを監査するには</span><span class="sxs-lookup"><span data-stu-id="cabcf-115">To audit Single Sign-On using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="cabcf-116">**開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、クリックして**SSO 管理**です。</span><span class="sxs-lookup"><span data-stu-id="cabcf-116">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="cabcf-117">ENTSSO MMC スナップインの [スコープ] ウィンドウで、展開、**エンタープライズ シングル サインオン**ノード。</span><span class="sxs-lookup"><span data-stu-id="cabcf-117">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="cabcf-118">右クリック**システム**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="cabcf-118">Right-click **System**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="cabcf-119">**システム プロパティ**ダイアログ ボックスで、をクリックして、**監査**タブです。</span><span class="sxs-lookup"><span data-stu-id="cabcf-119">On the  **System Properties** dialog box, click the **Audits** tab.</span></span>  
  
5.  <span data-ttu-id="cabcf-120">適切な設定を入力し、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="cabcf-120">Enter the appropriate settings, and click **OK**.</span></span>  
  
### <a name="to-audit-single-sign-on-using-the-command-line"></a><span data-ttu-id="cabcf-121">コマンド ラインでシングル サインオンを監査するには</span><span class="sxs-lookup"><span data-stu-id="cabcf-121">To audit Single Sign-On using the command line</span></span>  
  
1.  <span data-ttu-id="cabcf-122">**開始** メニューのをクリックして**実行**、し、入力**cmd**です。</span><span class="sxs-lookup"><span data-stu-id="cabcf-122">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="cabcf-123">コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="cabcf-123">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="cabcf-124">既定のインストール ディレクトリは**\<ドライブ\>**: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="cabcf-124">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="cabcf-125">型**ssoconfig – auditlevel\<正\>\<負\>**ここで、 **\<正\>**のレベルです操作が成功したときに監査と**\<負\>**操作が失敗したときの監査のレベルです。</span><span class="sxs-lookup"><span data-stu-id="cabcf-125">Type **ssoconfig –auditlevel \<positive\>\<negative\>**, where **\<positive\>** is the level of auditing when actions succeed, and **\<negative\>** is the level of auditing when actions fail.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cabcf-126">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="cabcf-126">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-audit-the-sso-database"></a><span data-ttu-id="cabcf-127">SSO データベースを監査するには</span><span class="sxs-lookup"><span data-stu-id="cabcf-127">To audit the SSO database</span></span>  
  
1.  <span data-ttu-id="cabcf-128">をクリックして**開始**、 をクリックして**実行**、し、入力**cmd**です。</span><span class="sxs-lookup"><span data-stu-id="cabcf-128">Click **Start**, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="cabcf-129">コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="cabcf-129">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="cabcf-130">既定のインストール ディレクトリは**\<ドライブ\>**: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="cabcf-130">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="cabcf-131">型**ssomanage – updatedb\<更新ファイル\>**ここで、 **\<更新ファイル\>**はパスとファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="cabcf-131">Type **ssomanage –updatedb \<update file\>**, where **\<update file\>**is the path and name of the file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cabcf-132">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="cabcf-132">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cabcf-133">参照</span><span class="sxs-lookup"><span data-stu-id="cabcf-133">See Also</span></span>  
 <span data-ttu-id="cabcf-134">[SSO データベースを更新する方法](../core/how-to-update-the-sso-database.md) </span><span class="sxs-lookup"><span data-stu-id="cabcf-134">[How to Update the SSO Database](../core/how-to-update-the-sso-database.md) </span></span>  
 [<span data-ttu-id="cabcf-135">SSO の使用</span><span class="sxs-lookup"><span data-stu-id="cabcf-135">Using SSO</span></span>](../core/using-sso.md)