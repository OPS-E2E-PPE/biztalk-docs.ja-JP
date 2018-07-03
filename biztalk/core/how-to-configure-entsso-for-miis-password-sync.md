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
ms.openlocfilehash: 9aed37b5b3883242005f46dcc6a0253a4971d680
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005227"
---
# <a name="how-to-configure-entsso-for-miis-password-sync"></a><span data-ttu-id="70e92-102">MIIS パスワード同期用に ENTSSO を構成する方法</span><span class="sxs-lookup"><span data-stu-id="70e92-102">How to Configure ENTSSO for MIIS Password Sync</span></span>
<span data-ttu-id="70e92-103">XML ファイルと Microsoft Identity Integration Server (MIIS) の構成が終わったら、残りの構成手順は、エンタープライズ シングル サインオン (ENTSSO) システムで行います。</span><span class="sxs-lookup"><span data-stu-id="70e92-103">After configuring the XML file and Microsoft Identity Integration Server (MIIS), the remaining configuration steps take place in the Enterprise Single Sign-On (ENTSSO) system.</span></span>  
  
### <a name="to-allow-password-sync-from-miis"></a><span data-ttu-id="70e92-104">MIIS からパスワード同期を有効にするには</span><span class="sxs-lookup"><span data-stu-id="70e92-104">To allow Password Sync from MIIS</span></span>  
  
1.  <span data-ttu-id="70e92-105">エンタープライズ シングル サインオン、クリックして、**サーバー**ノード。</span><span class="sxs-lookup"><span data-stu-id="70e92-105">In Enterprise Single Sign-On, click the **Servers** node.</span></span>  
  
2.  <span data-ttu-id="70e92-106">適切なサーバーを右クリックし、をクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="70e92-106">Right-click the appropriate server, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="70e92-107">をクリックして、**パスワード同期**タブ。</span><span class="sxs-lookup"><span data-stu-id="70e92-107">Click the **Password Sync** tab.</span></span>  
  
4.  <span data-ttu-id="70e92-108">選択**MIIS からパスワード同期を許可する**します。</span><span class="sxs-lookup"><span data-stu-id="70e92-108">Select **Allow password sync from MIIS**.</span></span>  
  
5.  <span data-ttu-id="70e92-109">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70e92-109">Click **OK**.</span></span>  
  
### <a name="to-enable-password-sync-on-the-system-level"></a><span data-ttu-id="70e92-110">パスワード同期をシステム レベルで有効にするには</span><span class="sxs-lookup"><span data-stu-id="70e92-110">To enable Password Sync on the system level</span></span>  
  
1. <span data-ttu-id="70e92-111">エンタープライズ シングル サインオンを右クリックし、**システム**ノード。</span><span class="sxs-lookup"><span data-stu-id="70e92-111">In Enterprise Single Sign-On, right-click the **System** node.</span></span>  
  
2. <span data-ttu-id="70e92-112">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70e92-112">Click **Properties**.</span></span>  
  
    <span data-ttu-id="70e92-113">**プロパティ** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="70e92-113">The **Properties** dialog box appears.</span></span>  
  
3. <span data-ttu-id="70e92-114">をクリックして、**オプション**タブ。</span><span class="sxs-lookup"><span data-stu-id="70e92-114">Click the **Options** tab.</span></span>  
  
4. <span data-ttu-id="70e92-115">**パスワード同期を有効にする**フィールドで、**アダプターから Windows**します。</span><span class="sxs-lookup"><span data-stu-id="70e92-115">In the **Enable Password Sync** field, select **From Windows to Adapters**.</span></span>  
  
    <span data-ttu-id="70e92-116">**追加の構成**</span><span class="sxs-lookup"><span data-stu-id="70e92-116">**Additional Configuration**</span></span>  
  
    <span data-ttu-id="70e92-117">最後に、次のいずれかを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70e92-117">Finally, you must configure one of the following:</span></span>  
  
   - <span data-ttu-id="70e92-118">Windows パスワード同期を受け入れるパスワード同期アダプタ</span><span class="sxs-lookup"><span data-stu-id="70e92-118">A Password Sync Adapter that accepts Windows Password Sync.</span></span>  
  
   - <span data-ttu-id="70e92-119">少なくとも 1 つのアプリケーションに対して有効になっている直接パスワード同期</span><span class="sxs-lookup"><span data-stu-id="70e92-119">Direct Password Sync enabled on at least one application.</span></span>  
  
     <span data-ttu-id="70e92-120">構成方法については、パスワード同期のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="70e92-120">For information about how to do this, refer to your Password Sync documentation.</span></span>  
  
### <a name="to-configure-the-entsso-ma-for-miis-password-sync"></a><span data-ttu-id="70e92-121">MIIS パスワード同期用に EntSSO MA を構成するには</span><span class="sxs-lookup"><span data-stu-id="70e92-121">To configure the EntSSO MA for MIIS Password Sync</span></span>  
  
1.  <span data-ttu-id="70e92-122">ENTSSO 管理エージェントで**プロパティ**] ページで [**拡張機能の構成**します。</span><span class="sxs-lookup"><span data-stu-id="70e92-122">On the ENTSSO Management Agent **Properties** page, click **Configure Extensions**.</span></span>  
  
2.  <span data-ttu-id="70e92-123">**パスワード拡張機能の接続情報**フィールドに、をクリックして**設定**します。</span><span class="sxs-lookup"><span data-stu-id="70e92-123">In the **Connection information for password extension** field, click **Settings**.</span></span>  
  
3.  <span data-ttu-id="70e92-124">**接続先**フィールド、パスワードの変更を受信するコンピュータの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="70e92-124">In the **Connect To** field enter the name of the computer that will receive the password changes.</span></span>  
  
     <span data-ttu-id="70e92-125">このコンピュータ名は、ドメインの ENTSSO サービスに対するサービス プリンシパル名 (SPN) を作成したときと同じ形式にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="70e92-125">The computer name must be in the same format that was used when creating the Service Principal Name (SPN) for the ENTSSO service on the domain.</span></span>  
  
     <span data-ttu-id="70e92-126">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="70e92-126">For example:</span></span>  
  
     <span data-ttu-id="70e92-127">短い形式の SPN である ENTSSO/ABCD1411 を作成した場合は、「ABCD1411」と入力します。</span><span class="sxs-lookup"><span data-stu-id="70e92-127">Short format - SPN = ENTSSO/ABCD1411, then enter ABCD1411</span></span>  
  
4.  <span data-ttu-id="70e92-128">長い形式の SPN である ENTSSO/ABCD1411.CompanyName.com を作成した場合は、「ABCD1411.CompanyName.com」と入力します。</span><span class="sxs-lookup"><span data-stu-id="70e92-128">Long format - SPN = ENTSSO/ABCD1411.CompanyName.com then enter ABCD1411.CompanyName.com</span></span>  
  
### <a name="additional-configuration-steps"></a><span data-ttu-id="70e92-129">追加の構成手順</span><span class="sxs-lookup"><span data-stu-id="70e92-129">Additional Configuration Steps</span></span>  
  
1.  <span data-ttu-id="70e92-130">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Identity Integration Server**、順にクリックします**Identity Manager**します。</span><span class="sxs-lookup"><span data-stu-id="70e92-130">Click **Start**, point to **All Programs**, point to **Microsoft Identity Integration Server**, and then click **Identity Manager**.</span></span>  
  
2.  <span data-ttu-id="70e92-131">**[ツール]** メニューの **[オプション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70e92-131">On the **Tools** menu, click **Options**.</span></span>  
  
3.  <span data-ttu-id="70e92-132">選択**パスワード同期を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="70e92-132">Select **Enable Password Synchronization**.</span></span>  
  
4.  <span data-ttu-id="70e92-133">**管理エージェントを表示**、 **ADMA**します。</span><span class="sxs-lookup"><span data-stu-id="70e92-133">In the **Management Agents view**, select **ADMA**.</span></span>  
  
5.  <span data-ttu-id="70e92-134">**アクション**ペインで、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="70e92-134">In the **Action** pane, select **Properties**.</span></span>  
  
6.  <span data-ttu-id="70e92-135">**プロパティ** ページで、**ディレクトリ パーティションの構成**、し、**パスワードの同期ソースとしてこのパーティションを有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="70e92-135">On the **Properties** page, select **Configure Directory Partitions**, and then select **Enable this partition as a password synchronization source**.</span></span>  
  
7.  <span data-ttu-id="70e92-136">クリックして**ターゲット**、し、ENTSSOMA2 が MIIS からパスワード変更を受信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="70e92-136">Click **Targets**, and then select ENTSSOMA2 to enable it to receive password changes from MIIS.</span></span> <span data-ttu-id="70e92-137">[ENTSSOMA] の選択を解除します。</span><span class="sxs-lookup"><span data-stu-id="70e92-137">Deselect ENTSSOMA.</span></span> <span data-ttu-id="70e92-138">をクリックして**OK**、順にクリックします**OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="70e92-138">Click **OK**, and then click **OK** again.</span></span>  
  
8.  <span data-ttu-id="70e92-139">**管理エージェント**ビューで、 **ENTSSOMA2**します。</span><span class="sxs-lookup"><span data-stu-id="70e92-139">In the **Management Agent** view, select **ENTSSOMA2**.</span></span> <span data-ttu-id="70e92-140">右側のウィンドウで次のように選択します。**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="70e92-140">In the right-hand pane, select **Properties**.</span></span> <span data-ttu-id="70e92-141">**プロパティ**] ページで [**拡張機能の構成**します。</span><span class="sxs-lookup"><span data-stu-id="70e92-141">On the **Properties** page, click **Configure Extensions**.</span></span>  
  
9. <span data-ttu-id="70e92-142">確認します**パスワード管理を有効にする**が選択されているし、をクリックし、**設定**します。</span><span class="sxs-lookup"><span data-stu-id="70e92-142">Confirm that **Enable password management** is selected, and then click **Settings**.</span></span>  
  
10. <span data-ttu-id="70e92-143">**接続設定**ダイアログ ボックスで、次を指定します。</span><span class="sxs-lookup"><span data-stu-id="70e92-143">In the **Connection Settings** dialog, specify the following:</span></span>  
  
    -   <span data-ttu-id="70e92-144">接続: INTSVR1.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="70e92-144">Connect To: INTSVR1.fabrikam.com</span></span>  
  
    -   <span data-ttu-id="70e92-145">ユーザー: fabrikam\ssosvcact</span><span class="sxs-lookup"><span data-stu-id="70e92-145">User: fabrikam\ssosvcact</span></span>  
  
    -   <span data-ttu-id="70e92-146">パスワード: ssosvcact</span><span class="sxs-lookup"><span data-stu-id="70e92-146">Password: ssosvcact</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="70e92-147">このアカウントは、INTSVR1.fabrikam.com に対して構成されている ENTSSO サービス アカウントと一致させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="70e92-147">This account should match the ENTSSO service account configured on INTSVR1.fabrikam.com.</span></span>  
  
11. <span data-ttu-id="70e92-148">をクリックして**OK**、順にクリックします**OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="70e92-148">Click **OK**, and then click **OK** again.</span></span>  
  
12. <span data-ttu-id="70e92-149">MIIS のパスワード同期を無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="70e92-149">You can also disable password sync for MIIS.</span></span> <span data-ttu-id="70e92-150">これを実行する**Identity Manager**、クリックして、**ツール** メニューのをクリックして**オプション**、選択を解除**パスワード同期を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="70e92-150">To do this, in **Identity Manager**, click the **Tools** menu, click **Options**, and then deselect **Enable Password Synchronization**.</span></span>  
  
     <span data-ttu-id="70e92-151">次の制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="70e92-151">The following restrictions will apply:</span></span>  
  
    -   <span data-ttu-id="70e92-152">パスワード同期を正しく機能させるには、ENTSSO 管理エージェントが通信する ENTSSO サービス アカウントに対して SPN を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70e92-152">For Password Sync to function properly, SPN must be configured on the ENTSSO service account that the ENTSSO Management Agent will communicate with.</span></span>  
  
    -   <span data-ttu-id="70e92-153">MIIS と ENTSSO サーバー間の通信には Kerberos が必要です。</span><span class="sxs-lookup"><span data-stu-id="70e92-153">Communication between MIIS and the ENTSSO server requires Kerberos.</span></span>  
  
13. <span data-ttu-id="70e92-154">ENTSSO 管理エージェントの MIIS 接続構成でパスワード拡張機能を構成する場合は、指定したアカウントが、MIIS からパスワードを受信する ENTSSO サーバーのサービス アカウントと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70e92-154">When configuring Password Extension in the MIIS connection configuration for the ENTSSO Management Agent, the account specified must match the service account for the ENTSSO server that will receive passwords from MIIS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70e92-155">参照</span><span class="sxs-lookup"><span data-stu-id="70e92-155">See Also</span></span>  
 [<span data-ttu-id="70e92-156">ENTSSO 管理エージェントを使用する方法</span><span class="sxs-lookup"><span data-stu-id="70e92-156">How to Use the ENTSSO Management Agent</span></span>](../core/how-to-use-the-entsso-management-agent.md)