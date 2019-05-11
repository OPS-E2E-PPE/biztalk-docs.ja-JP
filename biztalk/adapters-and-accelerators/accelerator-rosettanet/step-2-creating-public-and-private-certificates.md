---
title: 手順 2:パブリックおよびプライベート証明書の作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, creating certificates
- public certificates
- certificates, public certificates
- creating, certificates
- private certificates
ms.assetid: 0a925d89-03d9-41fe-907b-85a6ae42362a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef62e5ff78b7a8d0be417bbb89e5bba92132c3c0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281302"
---
# <a name="step-2-creating-public-and-private-certificates"></a><span data-ttu-id="32488-102">手順 2:パブリックおよびプライベート証明書の作成</span><span class="sxs-lookup"><span data-stu-id="32488-102">Step 2: Creating Public and Private Certificates</span></span>
<span data-ttu-id="32488-103">作成した証明機関を使用するこの手順で[手順 1。証明機関の作成&#91;RN3&#93; ](../../adapters-and-accelerators/accelerator-rosettanet/step-1-creating-a-certification-authority.md) Contoso と Fabrikam 組織で使用されるパブリックおよびプライベート証明書を生成します。</span><span class="sxs-lookup"><span data-stu-id="32488-103">In this step, you use the Certification Authority created in [Step 1: Creating a Certification Authority &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/step-1-creating-a-certification-authority.md) to generate the public and private certificates that the Contoso and Fabrikam organizations use.</span></span>  

### <a name="to-generate-the-contoso-and-fabrikam-encryption-certificates"></a><span data-ttu-id="32488-104">Contoso と Fabrikam の暗号化証明書を生成するには</span><span class="sxs-lookup"><span data-stu-id="32488-104">To generate the Contoso and Fabrikam encryption certificates</span></span>  

1. <span data-ttu-id="32488-105">Internet Explorer で、証明機関として使用するコンピューターを http://<contoso_computername>/certsrv を開きます。</span><span class="sxs-lookup"><span data-stu-id="32488-105">On the computer you used as the Certification Authority, in Internet Explorer, locate and open http://<contoso_computername>/certsrv.</span></span>  

2. <span data-ttu-id="32488-106">**ようこそ**] ページで [**証明書を要求**します。</span><span class="sxs-lookup"><span data-stu-id="32488-106">On the **Welcome** page, click **Request a certificate**.</span></span>  

3. <span data-ttu-id="32488-107">**証明書を要求**] ページで [**高度な証明書の要求**します。</span><span class="sxs-lookup"><span data-stu-id="32488-107">On the **Request a Certificate** page, click **advanced certificate request**.</span></span>  

4. <span data-ttu-id="32488-108">**証明書要求の高度な**] ページで [**作成し、この CA に要求を送信**。</span><span class="sxs-lookup"><span data-stu-id="32488-108">On the **Advanced Certificate Request** page, click **Create and submit a request to this CA**.</span></span>  

5. <span data-ttu-id="32488-109">**証明書の要求の高度な**ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="32488-109">On the **Advanced Certificate Request** page, do the following:</span></span>  


   |            <span data-ttu-id="32488-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="32488-110">Use this</span></span>            |                                                                         <span data-ttu-id="32488-111">目的</span><span class="sxs-lookup"><span data-stu-id="32488-111">To do this</span></span>                                                                         |
   |--------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |            <span data-ttu-id="32488-112">**名前**</span><span class="sxs-lookup"><span data-stu-id="32488-112">**Name**</span></span>            |                                                               <span data-ttu-id="32488-113">型**Fabrikam Encryption**します。</span><span class="sxs-lookup"><span data-stu-id="32488-113">Type **Fabrikam Encryption**.</span></span>                                                                |
   |           <span data-ttu-id="32488-114">**電子メール**</span><span class="sxs-lookup"><span data-stu-id="32488-114">**E-Mail**</span></span>           |                                                          <span data-ttu-id="32488-115">型 <strong>jdoe@fabrikam.com</strong>します。</span><span class="sxs-lookup"><span data-stu-id="32488-115">Type <strong>jdoe@fabrikam.com</strong>.</span></span>                                                          |
   |          <span data-ttu-id="32488-116">**企業**</span><span class="sxs-lookup"><span data-stu-id="32488-116">**Company**</span></span>           |                                                                     <span data-ttu-id="32488-117">型**Fabrikam**します。</span><span class="sxs-lookup"><span data-stu-id="32488-117">Type **Fabrikam**.</span></span>                                                                     |
   |         <span data-ttu-id="32488-118">**部門**</span><span class="sxs-lookup"><span data-stu-id="32488-118">**Department**</span></span>         |                                                                       <span data-ttu-id="32488-119">型**テスト**します。</span><span class="sxs-lookup"><span data-stu-id="32488-119">Type **Test**.</span></span>                                                                       |
   |            <span data-ttu-id="32488-120">**City**</span><span class="sxs-lookup"><span data-stu-id="32488-120">**City**</span></span>            |                                                                       <span data-ttu-id="32488-121">型**テスト**します。</span><span class="sxs-lookup"><span data-stu-id="32488-121">Type **Test**.</span></span>                                                                       |
   |           <span data-ttu-id="32488-122">**State**</span><span class="sxs-lookup"><span data-stu-id="32488-122">**State**</span></span>            |                                                                       <span data-ttu-id="32488-123">型**テスト**します。</span><span class="sxs-lookup"><span data-stu-id="32488-123">Type **Test**.</span></span>                                                                       |
   |       <span data-ttu-id="32488-124">**国/地域**</span><span class="sxs-lookup"><span data-stu-id="32488-124">**Country/Region**</span></span>       |                                                                        <span data-ttu-id="32488-125">型**米国**します。</span><span class="sxs-lookup"><span data-stu-id="32488-125">Type **US**.</span></span>                                                                        |
   | <span data-ttu-id="32488-126">**必要な証明書の種類**</span><span class="sxs-lookup"><span data-stu-id="32488-126">**Type of Certificate Needed**</span></span> |                                             <span data-ttu-id="32488-127">選択**電子メール保護証明書**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="32488-127">Select **E-Mail Protection Certificate** from the drop down list.</span></span>                                              |
   |         <span data-ttu-id="32488-128">**キー使用法**</span><span class="sxs-lookup"><span data-stu-id="32488-128">**Key Usage**</span></span>          |                                                              <span data-ttu-id="32488-129">選択、 **Exchange**オプション。</span><span class="sxs-lookup"><span data-stu-id="32488-129">Select the **Exchange** option.</span></span>                                                               |
   |   <span data-ttu-id="32488-130">**キーのオプション**</span><span class="sxs-lookup"><span data-stu-id="32488-130">**Additional Key Options**</span></span>   | <span data-ttu-id="32488-131">次のオプションでは、チェックを配置します。</span><span class="sxs-lookup"><span data-stu-id="32488-131">Place a check in the following options:</span></span><br /><br /> <span data-ttu-id="32488-132">-   **キー エクスポート可能としてマークします。**</span><span class="sxs-lookup"><span data-stu-id="32488-132">-   **Mark keys as exportable**</span></span><br /><span data-ttu-id="32488-133">-   **ローカル コンピューターの証明書ストアに証明書を格納します。**</span><span class="sxs-lookup"><span data-stu-id="32488-133">-   **Store certificate in the local computer certificate store**</span></span> |
   |       <span data-ttu-id="32488-134">**表示名**</span><span class="sxs-lookup"><span data-stu-id="32488-134">**Friendly Name**</span></span>        |                                                               <span data-ttu-id="32488-135">型**Fabrikam Encryption**します。</span><span class="sxs-lookup"><span data-stu-id="32488-135">Type **Fabrikam Encryption**.</span></span>                                                                |


6. <span data-ttu-id="32488-136">クリックして**送信**、順にクリックします**はい**で**Web アクセスの確認** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="32488-136">Click **Submit**, and then click **Yes** in **Web Access Confirmation** dialog box.</span></span>  

7. <span data-ttu-id="32488-137">**証明書は発行**] ページで [**この証明書をインストール**します。</span><span class="sxs-lookup"><span data-stu-id="32488-137">On the **Certificate Issued** page, click **Install this certificate**.</span></span>  

8. <span data-ttu-id="32488-138">手順 1 ~ 7 の情報を変更する、**名前**ボックスに、**識別情報**セクションおよび**フレンドリ名**ボックス**Contoso暗号化**します。</span><span class="sxs-lookup"><span data-stu-id="32488-138">Repeat steps 1-7, changing the information in the **Name** box in the **Identifying Information** section and the **Friendly Name** box to **Contoso Encryption**.</span></span>  

### <a name="to-generate-the-contoso-and-fabrikam-signing-certificates"></a><span data-ttu-id="32488-139">Contoso と Fabrikam の署名証明書を生成するには</span><span class="sxs-lookup"><span data-stu-id="32488-139">To generate the Contoso and Fabrikam Signing Certificates</span></span>  

1. <span data-ttu-id="32488-140">Internet Explorer を http://<contoso_computername>/certsrv を開きます。</span><span class="sxs-lookup"><span data-stu-id="32488-140">In Internet Explorer, locate and open http://<contoso_computername>/certsrv.</span></span>  

2. <span data-ttu-id="32488-141">**ようこそ**] ページで [**証明書を要求**します。</span><span class="sxs-lookup"><span data-stu-id="32488-141">On the **Welcome** page, click **Request a certificate**.</span></span>  

3. <span data-ttu-id="32488-142">**証明書を要求**] ページで [**高度な証明書の要求**します。</span><span class="sxs-lookup"><span data-stu-id="32488-142">On the **Request a Certificate** page, click **advanced certificate request**.</span></span>  

4. <span data-ttu-id="32488-143">**証明書要求の高度な**] ページで [**作成し、この CA に要求を送信**。</span><span class="sxs-lookup"><span data-stu-id="32488-143">On the **Advanced Certificate Request** page, click **Create and submit a request to this CA**.</span></span>  

5. <span data-ttu-id="32488-144">**証明書の要求の高度な**ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="32488-144">On the **Advanced Certificate Request** page, do the following:</span></span>  


   |            <span data-ttu-id="32488-145">プロパティ</span><span class="sxs-lookup"><span data-stu-id="32488-145">Use this</span></span>            |                                                                         <span data-ttu-id="32488-146">目的</span><span class="sxs-lookup"><span data-stu-id="32488-146">To do this</span></span>                                                                         |
   |--------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |            <span data-ttu-id="32488-147">**名前**</span><span class="sxs-lookup"><span data-stu-id="32488-147">**Name**</span></span>            |                                                                <span data-ttu-id="32488-148">型**Fabrikam Signature**します。</span><span class="sxs-lookup"><span data-stu-id="32488-148">Type **Fabrikam Signature**.</span></span>                                                                |
   |           <span data-ttu-id="32488-149">**電子メール**</span><span class="sxs-lookup"><span data-stu-id="32488-149">**E-Mail**</span></span>           |                                                          <span data-ttu-id="32488-150">型 <strong>jdoe@fabrikam.com</strong>します。</span><span class="sxs-lookup"><span data-stu-id="32488-150">Type <strong>jdoe@fabrikam.com</strong>.</span></span>                                                          |
   |          <span data-ttu-id="32488-151">**企業**</span><span class="sxs-lookup"><span data-stu-id="32488-151">**Company**</span></span>           |                                                                     <span data-ttu-id="32488-152">型**Fabrikam**します。</span><span class="sxs-lookup"><span data-stu-id="32488-152">Type **Fabrikam**.</span></span>                                                                     |
   |         <span data-ttu-id="32488-153">**部門**</span><span class="sxs-lookup"><span data-stu-id="32488-153">**Department**</span></span>         |                                                                       <span data-ttu-id="32488-154">型**テスト**します。</span><span class="sxs-lookup"><span data-stu-id="32488-154">Type **Test**.</span></span>                                                                       |
   |            <span data-ttu-id="32488-155">**City**</span><span class="sxs-lookup"><span data-stu-id="32488-155">**City**</span></span>            |                                                                       <span data-ttu-id="32488-156">型**テスト**します。</span><span class="sxs-lookup"><span data-stu-id="32488-156">Type **Test**.</span></span>                                                                       |
   |           <span data-ttu-id="32488-157">**State**</span><span class="sxs-lookup"><span data-stu-id="32488-157">**State**</span></span>            |                                                                       <span data-ttu-id="32488-158">型**テスト**します。</span><span class="sxs-lookup"><span data-stu-id="32488-158">Type **Test**.</span></span>                                                                       |
   |       <span data-ttu-id="32488-159">**国/地域**</span><span class="sxs-lookup"><span data-stu-id="32488-159">**Country/Region**</span></span>       |                                                                        <span data-ttu-id="32488-160">型**米国**します。</span><span class="sxs-lookup"><span data-stu-id="32488-160">Type **US**.</span></span>                                                                        |
   | <span data-ttu-id="32488-161">**必要な証明書の種類**</span><span class="sxs-lookup"><span data-stu-id="32488-161">**Type of Certificate Needed**</span></span> |                                             <span data-ttu-id="32488-162">選択**電子メール保護証明書**ドロップダウン リストをクリックします。</span><span class="sxs-lookup"><span data-stu-id="32488-162">Select **E-Mail Protection Certificate**.from the drop down list.</span></span>                                              |
   |         <span data-ttu-id="32488-163">**キー使用法**</span><span class="sxs-lookup"><span data-stu-id="32488-163">**Key Usage**</span></span>          |                                                              <span data-ttu-id="32488-164">選択、**署名**オプション。</span><span class="sxs-lookup"><span data-stu-id="32488-164">Select the **Signature** option.</span></span>                                                              |
   |   <span data-ttu-id="32488-165">**キーのオプション**</span><span class="sxs-lookup"><span data-stu-id="32488-165">**Additional Key Options**</span></span>   | <span data-ttu-id="32488-166">次のオプションでは、チェックを配置します。</span><span class="sxs-lookup"><span data-stu-id="32488-166">Place a check in the following options:</span></span><br /><br /> <span data-ttu-id="32488-167">-   **キー エクスポート可能としてマークします。**</span><span class="sxs-lookup"><span data-stu-id="32488-167">-   **Mark keys as exportable**</span></span><br /><span data-ttu-id="32488-168">-   **ローカル コンピューターの証明書ストアに証明書を格納します。**</span><span class="sxs-lookup"><span data-stu-id="32488-168">-   **Store certificate in the local computer certificate store**</span></span> |
   |       <span data-ttu-id="32488-169">**表示名**</span><span class="sxs-lookup"><span data-stu-id="32488-169">**Friendly Name**</span></span>        |                                                                <span data-ttu-id="32488-170">型**Fabrikam Signature**します。</span><span class="sxs-lookup"><span data-stu-id="32488-170">Type **Fabrikam Signature**.</span></span>                                                                |


6. <span data-ttu-id="32488-171">をクリックして**送信**、順にクリックします**はい**証明書を要求するように求められる場合。</span><span class="sxs-lookup"><span data-stu-id="32488-171">Click **Submit**, and then click **Yes** when asked to request the certificate.</span></span>  

7. <span data-ttu-id="32488-172">**証明書は発行**] ページで [**この証明書をインストール**します。</span><span class="sxs-lookup"><span data-stu-id="32488-172">On the **Certificate Issued** page, click **Install this certificate**.</span></span>  

8. <span data-ttu-id="32488-173">手順 1 ~ 7 の情報を変更する、**名前**ボックスに、**識別情報**セクションおよび**フレンドリ名**ボックス**Contoso署名**します。</span><span class="sxs-lookup"><span data-stu-id="32488-173">Repeat steps 1-7, changing the information in the **Name** box in the **Identifying Information** section and the **Friendly Name** box to **Contoso Signature**.</span></span>  

### <a name="to-generate-private-certificates-for-the-encryption-and-signature-certificates"></a><span data-ttu-id="32488-174">暗号化と署名証明書のプライベート証明書を生成するには</span><span class="sxs-lookup"><span data-stu-id="32488-174">To generate private certificates for the Encryption and Signature certificates</span></span>  

1.  <span data-ttu-id="32488-175">をクリックして**開始**、 をクリックして**実行**、型**MMC**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="32488-175">Click **Start**, click **Run**, type **MMC**, and then click **OK**.</span></span>  

2.  <span data-ttu-id="32488-176">コンソール 1 ウィンドウで、上、**ファイル** メニューのをクリックして**スナップインの追加と削除**します。</span><span class="sxs-lookup"><span data-stu-id="32488-176">In the Console1 window, on the **File** menu, click **Add/Remove Snap-in**.</span></span>  

3.  <span data-ttu-id="32488-177">スナップインの追加と削除 ダイアログ ボックスで、上、**スタンドアロン** タブで **追加**。</span><span class="sxs-lookup"><span data-stu-id="32488-177">In the Add/Remove Snap-in dialog box, on the **Standalone** tab, click **Add**.</span></span>  

4.  <span data-ttu-id="32488-178">スタンドアロン スナップインの追加 ダイアログ ボックスで、選択、**証明書**スナップインから、**利用できるスタンドアロン スナップイン**ボックスの一覧をクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="32488-178">In the Add Standalone Snap-in dialog box, select the **Certificates** snap-in from the **Available Standalone Snap-ins** list, and then click **Add**.</span></span>  

5.  <span data-ttu-id="32488-179">証明書スナップイン ダイアログ ボックスで、次のように選択します。 **ユーザー アカウント**、 をクリックし、**次**。</span><span class="sxs-lookup"><span data-stu-id="32488-179">In the Certificates snap-in dialog box, select **My user account**, and then click **Next**.</span></span>  

6.  <span data-ttu-id="32488-180">[コンピューターの選択] ダイアログ ボックスで、**完了**します。</span><span class="sxs-lookup"><span data-stu-id="32488-180">In the Select Computer dialog box, click **Finish**.</span></span>  

7.  <span data-ttu-id="32488-181">[スタンドアロン スナップインの追加] ダイアログ ボックスで、**閉じる**します。</span><span class="sxs-lookup"><span data-stu-id="32488-181">In the Add Standalone Snap-in dialog box, click **Close**.</span></span>  

8.  <span data-ttu-id="32488-182">[スナップインの追加と削除] ダイアログ ボックスで、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="32488-182">In the Add/Remove Snap-in dialog box, click **OK**.</span></span>  

9. <span data-ttu-id="32488-183">コンソール 1 ウィンドウで、**証明書 (ローカル コンピューター)**、展開**個人**、 をクリックし、**証明書**します。</span><span class="sxs-lookup"><span data-stu-id="32488-183">In the Console1 window, expand **Certificates (Local Computer)**, expand **Personal**, and then click **Certificates**.</span></span>  

10. <span data-ttu-id="32488-184">右側のウィンドウで右クリックし、 **Fabrikam Encryption**証明書をポイントして、**すべてのタスク**、 をクリックし、**エクスポート**。</span><span class="sxs-lookup"><span data-stu-id="32488-184">In the right pane, right-click the **Fabrikam Encryption** certificate, point to **All Tasks**, and then click **Export**.</span></span>  

11. <span data-ttu-id="32488-185">**証明書のエクスポート ウィザードへようこそ**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="32488-185">On the **Welcome to the Certificate Export Wizard** page, click **Next**.</span></span>  

12. <span data-ttu-id="32488-186">**秘密キーのエクスポート**] ページで、[**はい、秘密キーをエクスポート**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="32488-186">On the **Export Private Key** page, select **Yes, export the private key**, and then click **Next**.</span></span>  

13. <span data-ttu-id="32488-187">**エクスポート ファイルの形式**ことを確認します ページで、 **Personal Information Exchange**が唯一のオプションを選択すると、クリックして**次へ**します。</span><span class="sxs-lookup"><span data-stu-id="32488-187">On the **Export File Format** page, make sure that **Personal Information Exchange** is the only option selected, and then click **Next**.</span></span>  

14. <span data-ttu-id="32488-188">**パスワード** ページの 、**パスワード**と**パスワードの確認**ボックスに「 **mysecret**、 をクリックし、 **次へ**.</span><span class="sxs-lookup"><span data-stu-id="32488-188">On the **Password** page, in the **Password** and **Confirm Password** boxes, type **mysecret**, and then click **Next**.</span></span>  

15. <span data-ttu-id="32488-189">**ファイルにエクスポート**] ページで [**参照**します。</span><span class="sxs-lookup"><span data-stu-id="32488-189">On the **File To Export** page, click **Browse**.</span></span>  

16. <span data-ttu-id="32488-190">**付けて**ファイル パスを使用して証明書を保存 ダイアログ ボックスで、 *\<ドライブ\>*: \Certs\Fabrikam Private Encryption.pfx します。</span><span class="sxs-lookup"><span data-stu-id="32488-190">In the **Save As** dialog box, save the certificate using the file path *\<drive\>*:\Certs\Fabrikam Private Encryption.pfx.</span></span>  

17. <span data-ttu-id="32488-191">**エクスポートするファイル**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="32488-191">On the **File to Export** page, click **Next**.</span></span>  

18. <span data-ttu-id="32488-192">**証明書のエクスポート ウィザードの完了**] ページで [**完了**します。</span><span class="sxs-lookup"><span data-stu-id="32488-192">On the **Completing the Certificate Export Wizard** page, click **Finish**.</span></span>  

19. <span data-ttu-id="32488-193">エクスポートが成功を示す証明書のエクスポート ウィザード ポップアップで、次のようにクリックします。 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="32488-193">In the Certificate Export Wizard popup indicating a successful export, click **OK**.</span></span>  

20. <span data-ttu-id="32488-194">手順 10 ~ 19 ファイル名 Fabrikam Private Signature.pfx を使用して Fabrikam 署名証明書を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="32488-194">Repeat steps 10-19 for the Fabrikam Signature certificate using the file name Fabrikam Private Signature.pfx.</span></span>  

21. <span data-ttu-id="32488-195">手順 10 ~ 19 Contoso Private Signature.pfx と Contoso Private Encryption.pfx、ファイル名をそれぞれ使用して Contoso Signature および Contoso 暗号化証明書を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="32488-195">Repeat steps 10-19 for the Contoso Signature and Contoso Encryption certificates using the file names Contoso Private Signature.pfx and Contoso Private Encryption.pfx, respectively.</span></span>  

### <a name="to-generate-public-certificates-for-the-encryption-and-signature-certificates"></a><span data-ttu-id="32488-196">暗号化と署名証明書の公開証明書を生成するには</span><span class="sxs-lookup"><span data-stu-id="32488-196">To generate public certificates for the Encryption and Signature certificates</span></span>  

1.  <span data-ttu-id="32488-197">コンソール 1 ウィンドウで、**証明書-現在のユーザー**、展開**個人**、 をクリックし、**証明書**します。</span><span class="sxs-lookup"><span data-stu-id="32488-197">In the Console1 window, expand **Certificates – Current User**, expand **Personal**, and then click **Certificates**.</span></span>  

2.  <span data-ttu-id="32488-198">右クリックし、 **Fabrikam Encryption**証明書をポイントして、**すべてのタスク**、 をクリックし、**エクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="32488-198">Right-click the **Fabrikam Encryption** certificate, point to **All Tasks**, and then click **Export**.</span></span>  

3.  <span data-ttu-id="32488-199">**証明書のエクスポート ウィザードへようこそ**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="32488-199">On the **Welcome to the Certificate Export Wizard** page, click **Next**.</span></span>  

4.  <span data-ttu-id="32488-200">**秘密キーのエクスポート**] ページで、[**秘密キーをエクスポートしません**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="32488-200">On the **Export Private Key** page, select **No, do not export the private key**, and then click **Next**.</span></span>  

5.  <span data-ttu-id="32488-201">**エクスポート ファイルの形式**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="32488-201">On the **Export File Format** page, click **Next**.</span></span>  

6.  <span data-ttu-id="32488-202">**ファイルにエクスポート**] ページで [**参照**します。</span><span class="sxs-lookup"><span data-stu-id="32488-202">On the **File To Export** page, click **Browse**.</span></span>  

7.  <span data-ttu-id="32488-203">名前を付けて保存 ダイアログ ボックスで、次のように入力します**\<ドライブ\>: \Certs**の**で保存**、 **Fabrikam Public Encryption.cer**として**ファイル名。** と **\*.cer**の**型として保存**、 をクリックし、**保存**します。</span><span class="sxs-lookup"><span data-stu-id="32488-203">In the Save As dialog box, enter **\<drive\>:\Certs** for **Save in**, **Fabrikam Public Encryption.cer** as **File name**, and **\*.cer** for **Save as type**, and then click **Save**.</span></span>  

8.  <span data-ttu-id="32488-204">**エクスポートするファイル**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="32488-204">On the **File to Export** page, click **Next**.</span></span>  

9. <span data-ttu-id="32488-205">**証明書のエクスポート ウィザードの完了**] ページで [**完了**します。</span><span class="sxs-lookup"><span data-stu-id="32488-205">On the **Completing the Certificate Export Wizard** page, click **Finish**.</span></span>  

10. <span data-ttu-id="32488-206">エクスポートが成功を示す証明書のエクスポート ウィザード ポップアップで、次のようにクリックします。 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="32488-206">In the Certificate Export Wizard popup indicating a successful export, click **OK**.</span></span>  

11. <span data-ttu-id="32488-207">ファイル名 Fabrikam Public Signature.cer を使用して Fabrikam 署名証明書の手順 1 ~ 9 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="32488-207">Repeat steps 1-9 for the Fabrikam Signature certificate using the file name Fabrikam Public Signature.cer.</span></span>  

12. <span data-ttu-id="32488-208">Contoso Public Signature.cer と Contoso Public Encryption.cer、ファイル名をそれぞれ使用して Contoso Signature および Contoso 暗号化証明書の手順 1 ~ 9 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="32488-208">Repeat steps 1-9 for the Contoso Signature and Contoso Encryption certificates using the file names Contoso Public Signature.cer and Contoso Public Encryption.cer, respectively.</span></span>  

## <a name="see-also"></a><span data-ttu-id="32488-209">参照</span><span class="sxs-lookup"><span data-stu-id="32488-209">See Also</span></span>  
 [<span data-ttu-id="32488-210">ステップ 3:パブリック証明書とプライベート証明書のインポート</span><span class="sxs-lookup"><span data-stu-id="32488-210">Step 3: Importing Public and Private Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-importing-public-and-private-certificates.md)