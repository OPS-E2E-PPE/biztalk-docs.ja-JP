---
title: MIIS パスワード同期用に ENTSSO を構成する方法 |Microsoft Docs
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
ms.openlocfilehash: 9716e855a6eea34a7f24c534dabd57c8a628c960
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386320"
---
# <a name="how-to-configure-entsso-for-miis-password-sync"></a><span data-ttu-id="eb4cb-102">MIIS パスワード同期用に ENTSSO を構成する方法</span><span class="sxs-lookup"><span data-stu-id="eb4cb-102">How to Configure ENTSSO for MIIS Password Sync</span></span>
<span data-ttu-id="eb4cb-103">XML ファイルと Microsoft Identity Integration Server (MIIS) を構成した後、残りの構成手順は、エンタープライズ シングル サインオン (ENTSSO) システムで行います。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-103">After configuring the XML file and Microsoft Identity Integration Server (MIIS), the remaining configuration steps take place in the Enterprise Single Sign-On (ENTSSO) system.</span></span>  
  
### <a name="to-allow-password-sync-from-miis"></a><span data-ttu-id="eb4cb-104">MIIS からパスワード同期を許可するには</span><span class="sxs-lookup"><span data-stu-id="eb4cb-104">To allow Password Sync from MIIS</span></span>  
  
1.  <span data-ttu-id="eb4cb-105">エンタープライズ シングル サインオン、クリックして、**サーバー**ノード。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-105">In Enterprise Single Sign-On, click the **Servers** node.</span></span>  
  
2.  <span data-ttu-id="eb4cb-106">適切なサーバーを右クリックし、をクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-106">Right-click the appropriate server, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="eb4cb-107">をクリックして、**パスワード同期**タブ。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-107">Click the **Password Sync** tab.</span></span>  
  
4.  <span data-ttu-id="eb4cb-108">選択**MIIS からパスワード同期を許可する**します。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-108">Select **Allow password sync from MIIS**.</span></span>  
  
5.  <span data-ttu-id="eb4cb-109">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-109">Click **OK**.</span></span>  
  
### <a name="to-enable-password-sync-on-the-system-level"></a><span data-ttu-id="eb4cb-110">システム レベルでのパスワード同期を有効にするには</span><span class="sxs-lookup"><span data-stu-id="eb4cb-110">To enable Password Sync on the system level</span></span>  
  
1. <span data-ttu-id="eb4cb-111">エンタープライズ シングル サインオンを右クリックし、**システム**ノード。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-111">In Enterprise Single Sign-On, right-click the **System** node.</span></span>  
  
2. <span data-ttu-id="eb4cb-112">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-112">Click **Properties**.</span></span>  
  
    <span data-ttu-id="eb4cb-113">**プロパティ** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-113">The **Properties** dialog box appears.</span></span>  
  
3. <span data-ttu-id="eb4cb-114">をクリックして、**オプション**タブ。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-114">Click the **Options** tab.</span></span>  
  
4. <span data-ttu-id="eb4cb-115">**パスワード同期を有効にする**フィールドで、**アダプターから Windows**します。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-115">In the **Enable Password Sync** field, select **From Windows to Adapters**.</span></span>  
  
    <span data-ttu-id="eb4cb-116">**追加の構成**</span><span class="sxs-lookup"><span data-stu-id="eb4cb-116">**Additional Configuration**</span></span>  
  
    <span data-ttu-id="eb4cb-117">最後に、次のいずれかを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-117">Finally, you must configure one of the following:</span></span>  
  
   - <span data-ttu-id="eb4cb-118">Windows パスワード同期を受け入れるパスワード同期アダプター。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-118">A Password Sync Adapter that accepts Windows Password Sync.</span></span>  
  
   - <span data-ttu-id="eb4cb-119">直接パスワード同期を少なくとも 1 つのアプリケーションで有効にします。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-119">Direct Password Sync enabled on at least one application.</span></span>  
  
     <span data-ttu-id="eb4cb-120">これを行う方法については、パスワード同期は、マニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-120">For information about how to do this, refer to your Password Sync documentation.</span></span>  
  
### <a name="to-configure-the-entsso-ma-for-miis-password-sync"></a><span data-ttu-id="eb4cb-121">MIIS パスワード同期用に EntSSO MA を構成するには</span><span class="sxs-lookup"><span data-stu-id="eb4cb-121">To configure the EntSSO MA for MIIS Password Sync</span></span>  
  
1.  <span data-ttu-id="eb4cb-122">ENTSSO 管理エージェントで**プロパティ**] ページで [**拡張機能の構成**します。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-122">On the ENTSSO Management Agent **Properties** page, click **Configure Extensions**.</span></span>  
  
2.  <span data-ttu-id="eb4cb-123">**パスワード拡張機能の接続情報**フィールドに、をクリックして**設定**します。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-123">In the **Connection information for password extension** field, click **Settings**.</span></span>  
  
3.  <span data-ttu-id="eb4cb-124">**接続先**フィールド、パスワードの変更を受信するコンピュータの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-124">In the **Connect To** field enter the name of the computer that will receive the password changes.</span></span>  
  
     <span data-ttu-id="eb4cb-125">コンピューター名は、ドメインの ENTSSO サービスのサービス プリンシパル名 (SPN) を作成するときに使用されたのと同じ形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-125">The computer name must be in the same format that was used when creating the Service Principal Name (SPN) for the ENTSSO service on the domain.</span></span>  
  
     <span data-ttu-id="eb4cb-126">例 :</span><span class="sxs-lookup"><span data-stu-id="eb4cb-126">For example:</span></span>  
  
     <span data-ttu-id="eb4cb-127">短い形式の SPN ENTSSO/ABCD1411 を = し、ABCD1411 を入力します。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-127">Short format - SPN = ENTSSO/ABCD1411, then enter ABCD1411</span></span>  
  
4.  <span data-ttu-id="eb4cb-128">長い形式の SPN ENTSSO/ABCD1411.CompanyName.com を = し、ABCD1411.CompanyName.com を入力します。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-128">Long format - SPN = ENTSSO/ABCD1411.CompanyName.com then enter ABCD1411.CompanyName.com</span></span>  
  
### <a name="additional-configuration-steps"></a><span data-ttu-id="eb4cb-129">追加の構成手順</span><span class="sxs-lookup"><span data-stu-id="eb4cb-129">Additional Configuration Steps</span></span>  
  
1.  <span data-ttu-id="eb4cb-130">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Identity Integration Server**、順にクリックします**Identity Manager**します。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-130">Click **Start**, point to **All Programs**, point to **Microsoft Identity Integration Server**, and then click **Identity Manager**.</span></span>  
  
2.  <span data-ttu-id="eb4cb-131">**[ツール]** メニューの **[オプション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-131">On the **Tools** menu, click **Options**.</span></span>  
  
3.  <span data-ttu-id="eb4cb-132">選択**パスワード同期を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-132">Select **Enable Password Synchronization**.</span></span>  
  
4.  <span data-ttu-id="eb4cb-133">**管理エージェントを表示**、 **ADMA**します。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-133">In the **Management Agents view**, select **ADMA**.</span></span>  
  
5.  <span data-ttu-id="eb4cb-134">**アクション**ペインで、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-134">In the **Action** pane, select **Properties**.</span></span>  
  
6.  <span data-ttu-id="eb4cb-135">**プロパティ** ページで、**ディレクトリ パーティションの構成**、し、**パスワードの同期ソースとしてこのパーティションを有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-135">On the **Properties** page, select **Configure Directory Partitions**, and then select **Enable this partition as a password synchronization source**.</span></span>  
  
7.  <span data-ttu-id="eb4cb-136">クリックして**ターゲット**、し、ENTSSOMA2 が MIIS からパスワード変更を受信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-136">Click **Targets**, and then select ENTSSOMA2 to enable it to receive password changes from MIIS.</span></span> <span data-ttu-id="eb4cb-137">ENTSSOMA の選択を解除します。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-137">Deselect ENTSSOMA.</span></span> <span data-ttu-id="eb4cb-138">をクリックして**OK**、順にクリックします**OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-138">Click **OK**, and then click **OK** again.</span></span>  
  
8.  <span data-ttu-id="eb4cb-139">**管理エージェント**ビューで、 **ENTSSOMA2**します。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-139">In the **Management Agent** view, select **ENTSSOMA2**.</span></span> <span data-ttu-id="eb4cb-140">右側のウィンドウで次のように選択します。**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-140">In the right-hand pane, select **Properties**.</span></span> <span data-ttu-id="eb4cb-141">**プロパティ**] ページで [**拡張機能の構成**します。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-141">On the **Properties** page, click **Configure Extensions**.</span></span>  
  
9. <span data-ttu-id="eb4cb-142">確認します**パスワード管理を有効にする**が選択されているし、をクリックし、**設定**します。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-142">Confirm that **Enable password management** is selected, and then click **Settings**.</span></span>  
  
10. <span data-ttu-id="eb4cb-143">**接続設定**ダイアログ ボックスで、次を指定します。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-143">In the **Connection Settings** dialog, specify the following:</span></span>  
  
    -   <span data-ttu-id="eb4cb-144">接続します。INTSVR1.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="eb4cb-144">Connect To: INTSVR1.fabrikam.com</span></span>  
  
    -   <span data-ttu-id="eb4cb-145">ユーザー: fabrikam\ssosvcact</span><span class="sxs-lookup"><span data-stu-id="eb4cb-145">User: fabrikam\ssosvcact</span></span>  
  
    -   <span data-ttu-id="eb4cb-146">パスワード: ssosvcact</span><span class="sxs-lookup"><span data-stu-id="eb4cb-146">Password: ssosvcact</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="eb4cb-147">このアカウントは、INTSVR1.fabrikam.com に対して構成されている ENTSSO サービス アカウントと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-147">This account should match the ENTSSO service account configured on INTSVR1.fabrikam.com.</span></span>  
  
11. <span data-ttu-id="eb4cb-148">をクリックして**OK**、順にクリックします**OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-148">Click **OK**, and then click **OK** again.</span></span>  
  
12. <span data-ttu-id="eb4cb-149">MIIS のパスワード同期を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-149">You can also disable password sync for MIIS.</span></span> <span data-ttu-id="eb4cb-150">これを実行する**Identity Manager**、クリックして、**ツール** メニューのをクリックして**オプション**、選択を解除**パスワード同期を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-150">To do this, in **Identity Manager**, click the **Tools** menu, click **Options**, and then deselect **Enable Password Synchronization**.</span></span>  
  
     <span data-ttu-id="eb4cb-151">次の制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-151">The following restrictions will apply:</span></span>  
  
    -   <span data-ttu-id="eb4cb-152">パスワード同期が正常に機能する、ENTSSO 管理エージェントと通信する ENTSSO サービス アカウントの SPN を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-152">For Password Sync to function properly, SPN must be configured on the ENTSSO service account that the ENTSSO Management Agent will communicate with.</span></span>  
  
    -   <span data-ttu-id="eb4cb-153">MIIS と ENTSSO サーバー間の通信には、Kerberos が必要です。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-153">Communication between MIIS and the ENTSSO server requires Kerberos.</span></span>  
  
13. <span data-ttu-id="eb4cb-154">ENTSSO 管理エージェントの MIIS 接続構成でパスワード拡張機能を構成するときに、指定されたアカウントは、MIIS からパスワードを受信する ENTSSO サーバーのサービス アカウントと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb4cb-154">When configuring Password Extension in the MIIS connection configuration for the ENTSSO Management Agent, the account specified must match the service account for the ENTSSO server that will receive passwords from MIIS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb4cb-155">参照</span><span class="sxs-lookup"><span data-stu-id="eb4cb-155">See Also</span></span>  
 [<span data-ttu-id="eb4cb-156">ENTSSO 管理エージェントを使用する方法</span><span class="sxs-lookup"><span data-stu-id="eb4cb-156">How to Use the ENTSSO Management Agent</span></span>](../core/how-to-use-the-entsso-management-agent.md)