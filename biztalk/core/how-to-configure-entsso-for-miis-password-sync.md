---
title: MIIS パスワード同期用に ENTSSO を構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 89438935-37c1-4ac9-9ca2-7af8d9bfd3ae
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a1587c2e3c0d2164a7ffd3842b3d74df5b04685
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248946"
---
# <a name="how-to-configure-entsso-for-miis-password-sync"></a><span data-ttu-id="62741-102">MIIS パスワード同期用に ENTSSO を構成する方法</span><span class="sxs-lookup"><span data-stu-id="62741-102">How to Configure ENTSSO for MIIS Password Sync</span></span>
<span data-ttu-id="62741-103">XML ファイルと Microsoft Identity Integration Server (MIIS) の構成が終わったら、残りの構成手順は、エンタープライズ シングル サインオン (ENTSSO) システムで行います。</span><span class="sxs-lookup"><span data-stu-id="62741-103">After configuring the XML file and Microsoft Identity Integration Server (MIIS), the remaining configuration steps take place in the Enterprise Single Sign-On (ENTSSO) system.</span></span>  
  
### <a name="to-allow-password-sync-from-miis"></a><span data-ttu-id="62741-104">MIIS からパスワード同期を有効にするには</span><span class="sxs-lookup"><span data-stu-id="62741-104">To allow Password Sync from MIIS</span></span>  
  
1.  <span data-ttu-id="62741-105">エンタープライズ シングル サインオンをクリックして、**サーバー**ノード。</span><span class="sxs-lookup"><span data-stu-id="62741-105">In Enterprise Single Sign-On, click the **Servers** node.</span></span>  
  
2.  <span data-ttu-id="62741-106">適切なサーバーを右クリックし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="62741-106">Right-click the appropriate server, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="62741-107">クリックして、**パスワード同期**タブです。</span><span class="sxs-lookup"><span data-stu-id="62741-107">Click the **Password Sync** tab.</span></span>  
  
4.  <span data-ttu-id="62741-108">選択**MIIS からパスワード同期を許可する**です。</span><span class="sxs-lookup"><span data-stu-id="62741-108">Select **Allow password sync from MIIS**.</span></span>  
  
5.  <span data-ttu-id="62741-109">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62741-109">Click **OK**.</span></span>  
  
### <a name="to-enable-password-sync-on-the-system-level"></a><span data-ttu-id="62741-110">パスワード同期をシステム レベルで有効にするには</span><span class="sxs-lookup"><span data-stu-id="62741-110">To enable Password Sync on the system level</span></span>  
  
1.  <span data-ttu-id="62741-111">エンタープライズ シングル サインオンを右クリックし、**システム**ノード。</span><span class="sxs-lookup"><span data-stu-id="62741-111">In Enterprise Single Sign-On, right-click the **System** node.</span></span>  
  
2.  <span data-ttu-id="62741-112">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62741-112">Click **Properties**.</span></span>  
  
     <span data-ttu-id="62741-113">**プロパティ** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="62741-113">The **Properties** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="62741-114">クリックして、**オプション**タブです。</span><span class="sxs-lookup"><span data-stu-id="62741-114">Click the **Options** tab.</span></span>  
  
4.  <span data-ttu-id="62741-115">**パスワード同期を有効にする**フィールドで、 **Windows からアダプタへ**です。</span><span class="sxs-lookup"><span data-stu-id="62741-115">In the **Enable Password Sync** field, select **From Windows to Adapters**.</span></span>  
  
     <span data-ttu-id="62741-116">**追加の構成**</span><span class="sxs-lookup"><span data-stu-id="62741-116">**Additional Configuration**</span></span>  
  
     <span data-ttu-id="62741-117">最後に、次のいずれかを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62741-117">Finally, you must configure one of the following:</span></span>  
  
    -   <span data-ttu-id="62741-118">Windows パスワード同期を受け入れるパスワード同期アダプタ</span><span class="sxs-lookup"><span data-stu-id="62741-118">A Password Sync Adapter that accepts Windows Password Sync.</span></span>  
  
    -   <span data-ttu-id="62741-119">少なくとも 1 つのアプリケーションに対して有効になっている直接パスワード同期</span><span class="sxs-lookup"><span data-stu-id="62741-119">Direct Password Sync enabled on at least one application.</span></span>  
  
     <span data-ttu-id="62741-120">構成方法については、パスワード同期のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="62741-120">For information about how to do this, refer to your Password Sync documentation.</span></span>  
  
### <a name="to-configure-the-entsso-ma-for-miis-password-sync"></a><span data-ttu-id="62741-121">MIIS パスワード同期用に EntSSO MA を構成するには</span><span class="sxs-lookup"><span data-stu-id="62741-121">To configure the EntSSO MA for MIIS Password Sync</span></span>  
  
1.  <span data-ttu-id="62741-122">ENTSSO 管理エージェントで**プロパティ**] ページで [**拡張機能の構成**です。</span><span class="sxs-lookup"><span data-stu-id="62741-122">On the ENTSSO Management Agent **Properties** page, click **Configure Extensions**.</span></span>  
  
2.  <span data-ttu-id="62741-123">**パスワード拡張機能の接続情報を**フィールドで、をクリックして**設定**です。</span><span class="sxs-lookup"><span data-stu-id="62741-123">In the **Connection information for password extension** field, click **Settings**.</span></span>  
  
3.  <span data-ttu-id="62741-124">**Connect To**フィールドにパスワードの変更を受信するコンピューターの名前を入力してください。</span><span class="sxs-lookup"><span data-stu-id="62741-124">In the **Connect To** field enter the name of the computer that will receive the password changes.</span></span>  
  
     <span data-ttu-id="62741-125">このコンピュータ名は、ドメインの ENTSSO サービスに対するサービス プリンシパル名 (SPN) を作成したときと同じ形式にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="62741-125">The computer name must be in the same format that was used when creating the Service Principal Name (SPN) for the ENTSSO service on the domain.</span></span>  
  
     <span data-ttu-id="62741-126">例:</span><span class="sxs-lookup"><span data-stu-id="62741-126">For example:</span></span>  
  
     <span data-ttu-id="62741-127">短い形式の SPN である ENTSSO/ABCD1411 を作成した場合は、「ABCD1411」と入力します。</span><span class="sxs-lookup"><span data-stu-id="62741-127">Short format - SPN = ENTSSO/ABCD1411, then enter ABCD1411</span></span>  
  
4.  <span data-ttu-id="62741-128">長い形式の SPN である ENTSSO/ABCD1411.CompanyName.com を作成した場合は、「ABCD1411.CompanyName.com」と入力します。</span><span class="sxs-lookup"><span data-stu-id="62741-128">Long format - SPN = ENTSSO/ABCD1411.CompanyName.com then enter ABCD1411.CompanyName.com</span></span>  
  
### <a name="additional-configuration-steps"></a><span data-ttu-id="62741-129">追加の構成手順</span><span class="sxs-lookup"><span data-stu-id="62741-129">Additional Configuration Steps</span></span>  
  
1.  <span data-ttu-id="62741-130">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Identity Integration Server**、順にクリック**Identity Manager**です。</span><span class="sxs-lookup"><span data-stu-id="62741-130">Click **Start**, point to **All Programs**, point to **Microsoft Identity Integration Server**, and then click **Identity Manager**.</span></span>  
  
2.  <span data-ttu-id="62741-131">**[ツール]** メニューの **[オプション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62741-131">On the **Tools** menu, click **Options**.</span></span>  
  
3.  <span data-ttu-id="62741-132">選択**パスワード同期を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="62741-132">Select **Enable Password Synchronization**.</span></span>  
  
4.  <span data-ttu-id="62741-133">**管理エージェントを表示** **ADMA**です。</span><span class="sxs-lookup"><span data-stu-id="62741-133">In the **Management Agents view**, select **ADMA**.</span></span>  
  
5.  <span data-ttu-id="62741-134">**アクション**ペインで、**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="62741-134">In the **Action** pane, select **Properties**.</span></span>  
  
6.  <span data-ttu-id="62741-135">**プロパティ** ページで、**ディレクトリ パーティションを構成する**、し、**パスワードの同期ソースとしてこのパーティションを有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="62741-135">On the **Properties** page, select **Configure Directory Partitions**, and then select **Enable this partition as a password synchronization source**.</span></span>  
  
7.  <span data-ttu-id="62741-136">をクリックして**ターゲット**、し、ENTSSOMA2 が MIIS からパスワード変更を受信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="62741-136">Click **Targets**, and then select ENTSSOMA2 to enable it to receive password changes from MIIS.</span></span> <span data-ttu-id="62741-137">[ENTSSOMA] の選択を解除します。</span><span class="sxs-lookup"><span data-stu-id="62741-137">Deselect ENTSSOMA.</span></span> <span data-ttu-id="62741-138">をクリックして **[ok]**、順にクリック**OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="62741-138">Click **OK**, and then click **OK** again.</span></span>  
  
8.  <span data-ttu-id="62741-139">**管理エージェント**ビューで、 **ENTSSOMA2**です。</span><span class="sxs-lookup"><span data-stu-id="62741-139">In the **Management Agent** view, select **ENTSSOMA2**.</span></span> <span data-ttu-id="62741-140">右側のペインで選択**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="62741-140">In the right-hand pane, select **Properties**.</span></span> <span data-ttu-id="62741-141">**プロパティ**] ページで [**拡張機能の構成**です。</span><span class="sxs-lookup"><span data-stu-id="62741-141">On the **Properties** page, click **Configure Extensions**.</span></span>  
  
9. <span data-ttu-id="62741-142">いることを確認**パスワード管理を有効にする**を選択して、をクリックして**設定**です。</span><span class="sxs-lookup"><span data-stu-id="62741-142">Confirm that **Enable password management** is selected, and then click **Settings**.</span></span>  
  
10. <span data-ttu-id="62741-143">**接続設定**ダイアログ ボックスで、次の指定します。</span><span class="sxs-lookup"><span data-stu-id="62741-143">In the **Connection Settings** dialog, specify the following:</span></span>  
  
    -   <span data-ttu-id="62741-144">接続: INTSVR1.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="62741-144">Connect To: INTSVR1.fabrikam.com</span></span>  
  
    -   <span data-ttu-id="62741-145">ユーザー: fabrikam\ssosvcact</span><span class="sxs-lookup"><span data-stu-id="62741-145">User: fabrikam\ssosvcact</span></span>  
  
    -   <span data-ttu-id="62741-146">パスワード: ssosvcact</span><span class="sxs-lookup"><span data-stu-id="62741-146">Password: ssosvcact</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="62741-147">このアカウントは、INTSVR1.fabrikam.com に対して構成されている ENTSSO サービス アカウントと一致させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="62741-147">This account should match the ENTSSO service account configured on INTSVR1.fabrikam.com.</span></span>  
  
11. <span data-ttu-id="62741-148">をクリックして **[ok]**、順にクリック**OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="62741-148">Click **OK**, and then click **OK** again.</span></span>  
  
12. <span data-ttu-id="62741-149">MIIS のパスワード同期を無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="62741-149">You can also disable password sync for MIIS.</span></span> <span data-ttu-id="62741-150">これを行うに**Identity Manager**をクリックして、**ツール** メニューのをクリックして**オプション**、選択を解除**パスワード同期を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="62741-150">To do this, in **Identity Manager**, click the **Tools** menu, click **Options**, and then deselect **Enable Password Synchronization**.</span></span>  
  
     <span data-ttu-id="62741-151">次の制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="62741-151">The following restrictions will apply:</span></span>  
  
    -   <span data-ttu-id="62741-152">パスワード同期を正しく機能させるには、ENTSSO 管理エージェントが通信する ENTSSO サービス アカウントに対して SPN を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62741-152">For Password Sync to function properly, SPN must be configured on the ENTSSO service account that the ENTSSO Management Agent will communicate with.</span></span>  
  
    -   <span data-ttu-id="62741-153">MIIS と ENTSSO サーバー間の通信には Kerberos が必要です。</span><span class="sxs-lookup"><span data-stu-id="62741-153">Communication between MIIS and the ENTSSO server requires Kerberos.</span></span>  
  
13. <span data-ttu-id="62741-154">ENTSSO 管理エージェントの MIIS 接続構成でパスワード拡張機能を構成する場合は、指定したアカウントが、MIIS からパスワードを受信する ENTSSO サーバーのサービス アカウントと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62741-154">When configuring Password Extension in the MIIS connection configuration for the ENTSSO Management Agent, the account specified must match the service account for the ENTSSO server that will receive passwords from MIIS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62741-155">参照</span><span class="sxs-lookup"><span data-stu-id="62741-155">See Also</span></span>  
 [<span data-ttu-id="62741-156">ENTSSO 管理エージェントを使用する方法</span><span class="sxs-lookup"><span data-stu-id="62741-156">How to Use the ENTSSO Management Agent</span></span>](../core/how-to-use-the-entsso-management-agent.md)