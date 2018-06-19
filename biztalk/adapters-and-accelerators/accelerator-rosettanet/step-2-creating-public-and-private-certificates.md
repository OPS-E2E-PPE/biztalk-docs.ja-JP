---
title: '手順 2: パブリックおよびプライベート証明書の作成 |Microsoft ドキュメント'
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
ms.openlocfilehash: 7c26765b19c868dbb78d3924069b60161827312c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967600"
---
# <a name="step-2-creating-public-and-private-certificates"></a><span data-ttu-id="53db6-102">手順 2: パブリックおよびプライベート証明書の作成</span><span class="sxs-lookup"><span data-stu-id="53db6-102">Step 2: Creating Public and Private Certificates</span></span>
<span data-ttu-id="53db6-103">この手順で作成した証明機関を使用する[手順 1: 証明機関 &#91; を作成します。RN3 &#93;](../../adapters-and-accelerators/accelerator-rosettanet/step-1-creating-a-certification-authority.md)を使用して、Contoso と Fabrikam 組織パブリックおよびプライベート証明書を生成します。</span><span class="sxs-lookup"><span data-stu-id="53db6-103">In this step, you use the Certification Authority created in [Step 1: Creating a Certification Authority &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/step-1-creating-a-certification-authority.md) to generate the public and private certificates that the Contoso and Fabrikam organizations use.</span></span>  
  
### <a name="to-generate-the-contoso-and-fabrikam-encryption-certificates"></a><span data-ttu-id="53db6-104">Contoso および Fabrikam の暗号化証明書を生成するには</span><span class="sxs-lookup"><span data-stu-id="53db6-104">To generate the Contoso and Fabrikam encryption certificates</span></span>  
  
1.  <span data-ttu-id="53db6-105">証明機関として使用したコンピューターから、Internet Explorer を使用して http://<Contoso のコンピューター名>/certsrv を開きます。</span><span class="sxs-lookup"><span data-stu-id="53db6-105">On the computer you used as the Certification Authority, in Internet Explorer, locate and open http://<contoso_computername>/certsrv.</span></span>  
  
2.  <span data-ttu-id="53db6-106">**ようこそ** ページで、をクリックして**証明書を要求**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-106">On the **Welcome** page, click **Request a certificate**.</span></span>  
  
3.  <span data-ttu-id="53db6-107">**証明書を要求**] ページで [**高度な証明書の要求**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-107">On the **Request a Certificate** page, click **advanced certificate request**.</span></span>  
  
4.  <span data-ttu-id="53db6-108">**証明書の要求の高度な** ページで、をクリックして**作成してこの CA への要求を送信**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-108">On the **Advanced Certificate Request** page, click **Create and submit a request to this CA**.</span></span>  
  
5.  <span data-ttu-id="53db6-109">**証明書の要求の高度な** ページで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="53db6-109">On the **Advanced Certificate Request** page, do the following:</span></span>  
  
    |<span data-ttu-id="53db6-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="53db6-110">Use this</span></span>|<span data-ttu-id="53db6-111">目的</span><span class="sxs-lookup"><span data-stu-id="53db6-111">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="53db6-112">**名前**</span><span class="sxs-lookup"><span data-stu-id="53db6-112">**Name**</span></span>|<span data-ttu-id="53db6-113">型**Fabrikam Encryption**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-113">Type **Fabrikam Encryption**.</span></span>|  
    |<span data-ttu-id="53db6-114">**電子メール**</span><span class="sxs-lookup"><span data-stu-id="53db6-114">**E-Mail**</span></span>|<span data-ttu-id="53db6-115">型 **jdoe@fabrikam.com**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-115">Type **jdoe@fabrikam.com**.</span></span>|  
    |<span data-ttu-id="53db6-116">**Company**</span><span class="sxs-lookup"><span data-stu-id="53db6-116">**Company**</span></span>|<span data-ttu-id="53db6-117">型**Fabrikam**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-117">Type **Fabrikam**.</span></span>|  
    |<span data-ttu-id="53db6-118">**部門**</span><span class="sxs-lookup"><span data-stu-id="53db6-118">**Department**</span></span>|<span data-ttu-id="53db6-119">型**テスト**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-119">Type **Test**.</span></span>|  
    |<span data-ttu-id="53db6-120">**City**</span><span class="sxs-lookup"><span data-stu-id="53db6-120">**City**</span></span>|<span data-ttu-id="53db6-121">型**テスト**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-121">Type **Test**.</span></span>|  
    |<span data-ttu-id="53db6-122">**状態**</span><span class="sxs-lookup"><span data-stu-id="53db6-122">**State**</span></span>|<span data-ttu-id="53db6-123">型**テスト**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-123">Type **Test**.</span></span>|  
    |<span data-ttu-id="53db6-124">**国/地域**</span><span class="sxs-lookup"><span data-stu-id="53db6-124">**Country/Region**</span></span>|<span data-ttu-id="53db6-125">型**米国**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-125">Type **US**.</span></span>|  
    |<span data-ttu-id="53db6-126">**必要な証明書の種類**</span><span class="sxs-lookup"><span data-stu-id="53db6-126">**Type of Certificate Needed**</span></span>|<span data-ttu-id="53db6-127">選択**電子メール保護証明書**ドロップ ダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="53db6-127">Select **E-Mail Protection Certificate** from the drop down list.</span></span>|  
    |<span data-ttu-id="53db6-128">**キー使用法**</span><span class="sxs-lookup"><span data-stu-id="53db6-128">**Key Usage**</span></span>|<span data-ttu-id="53db6-129">選択、 **Exchange**オプション。</span><span class="sxs-lookup"><span data-stu-id="53db6-129">Select the **Exchange** option.</span></span>|  
    |<span data-ttu-id="53db6-130">**キーのオプション**</span><span class="sxs-lookup"><span data-stu-id="53db6-130">**Additional Key Options**</span></span>|<span data-ttu-id="53db6-131">次のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="53db6-131">Place a check in the following options:</span></span><br /><br /> <span data-ttu-id="53db6-132">-   **キー エクスポート可能としてマークします。**</span><span class="sxs-lookup"><span data-stu-id="53db6-132">-   **Mark keys as exportable**</span></span><br /><span data-ttu-id="53db6-133">-   **ローカル コンピューター証明書ストアに証明書を保存します。**</span><span class="sxs-lookup"><span data-stu-id="53db6-133">-   **Store certificate in the local computer certificate store**</span></span>|  
    |<span data-ttu-id="53db6-134">**表示名**</span><span class="sxs-lookup"><span data-stu-id="53db6-134">**Friendly Name**</span></span>|<span data-ttu-id="53db6-135">型**Fabrikam Encryption**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-135">Type **Fabrikam Encryption**.</span></span>|  
  
6.  <span data-ttu-id="53db6-136">をクリックして**送信**、順にクリック**はい**で**Web アクセスの確認** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="53db6-136">Click **Submit**, and then click **Yes** in **Web Access Confirmation** dialog box.</span></span>  
  
7.  <span data-ttu-id="53db6-137">**証明書は発行**] ページで [**この証明書をインストール**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-137">On the **Certificate Issued** page, click **Install this certificate**.</span></span>  
  
8.  <span data-ttu-id="53db6-138">手順 1. ~ 7. で情報を変更する、**名前**ボックスに、**識別情報**セクションおよび**フレンドリ名**ボックス**Contoso暗号化**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-138">Repeat steps 1-7, changing the information in the **Name** box in the **Identifying Information** section and the **Friendly Name** box to **Contoso Encryption**.</span></span>  
  
### <a name="to-generate-the-contoso-and-fabrikam-signing-certificates"></a><span data-ttu-id="53db6-139">Contoso および Fabrikam の署名証明書を生成するには</span><span class="sxs-lookup"><span data-stu-id="53db6-139">To generate the Contoso and Fabrikam Signing Certificates</span></span>  
  
1.  <span data-ttu-id="53db6-140">Internet Explorer で、http://<Contoso のコンピューター名>/certsrv を検索して開きます。</span><span class="sxs-lookup"><span data-stu-id="53db6-140">In Internet Explorer, locate and open http://<contoso_computername>/certsrv.</span></span>  
  
2.  <span data-ttu-id="53db6-141">**ようこそ** ページで、をクリックして**証明書を要求**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-141">On the **Welcome** page, click **Request a certificate**.</span></span>  
  
3.  <span data-ttu-id="53db6-142">**証明書を要求**] ページで [**高度な証明書の要求**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-142">On the **Request a Certificate** page, click **advanced certificate request**.</span></span>  
  
4.  <span data-ttu-id="53db6-143">**証明書の要求の高度な** ページで、をクリックして**作成してこの CA への要求を送信**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-143">On the **Advanced Certificate Request** page, click **Create and submit a request to this CA**.</span></span>  
  
5.  <span data-ttu-id="53db6-144">**証明書の要求の高度な** ページで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="53db6-144">On the **Advanced Certificate Request** page, do the following:</span></span>  
  
    |<span data-ttu-id="53db6-145">プロパティ</span><span class="sxs-lookup"><span data-stu-id="53db6-145">Use this</span></span>|<span data-ttu-id="53db6-146">目的</span><span class="sxs-lookup"><span data-stu-id="53db6-146">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="53db6-147">**名前**</span><span class="sxs-lookup"><span data-stu-id="53db6-147">**Name**</span></span>|<span data-ttu-id="53db6-148">型**Fabrikam Signature**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-148">Type **Fabrikam Signature**.</span></span>|  
    |<span data-ttu-id="53db6-149">**電子メール**</span><span class="sxs-lookup"><span data-stu-id="53db6-149">**E-Mail**</span></span>|<span data-ttu-id="53db6-150">型 **jdoe@fabrikam.com**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-150">Type **jdoe@fabrikam.com**.</span></span>|  
    |<span data-ttu-id="53db6-151">**Company**</span><span class="sxs-lookup"><span data-stu-id="53db6-151">**Company**</span></span>|<span data-ttu-id="53db6-152">型**Fabrikam**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-152">Type **Fabrikam**.</span></span>|  
    |<span data-ttu-id="53db6-153">**部門**</span><span class="sxs-lookup"><span data-stu-id="53db6-153">**Department**</span></span>|<span data-ttu-id="53db6-154">型**テスト**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-154">Type **Test**.</span></span>|  
    |<span data-ttu-id="53db6-155">**City**</span><span class="sxs-lookup"><span data-stu-id="53db6-155">**City**</span></span>|<span data-ttu-id="53db6-156">型**テスト**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-156">Type **Test**.</span></span>|  
    |<span data-ttu-id="53db6-157">**状態**</span><span class="sxs-lookup"><span data-stu-id="53db6-157">**State**</span></span>|<span data-ttu-id="53db6-158">型**テスト**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-158">Type **Test**.</span></span>|  
    |<span data-ttu-id="53db6-159">**国/地域**</span><span class="sxs-lookup"><span data-stu-id="53db6-159">**Country/Region**</span></span>|<span data-ttu-id="53db6-160">型**米国**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-160">Type **US**.</span></span>|  
    |<span data-ttu-id="53db6-161">**必要な証明書の種類**</span><span class="sxs-lookup"><span data-stu-id="53db6-161">**Type of Certificate Needed**</span></span>|<span data-ttu-id="53db6-162">選択**電子メール保護証明書**ドロップ ダウン リストの場合。</span><span class="sxs-lookup"><span data-stu-id="53db6-162">Select **E-Mail Protection Certificate**.from the drop down list.</span></span>|  
    |<span data-ttu-id="53db6-163">**キー使用法**</span><span class="sxs-lookup"><span data-stu-id="53db6-163">**Key Usage**</span></span>|<span data-ttu-id="53db6-164">選択、**署名**オプション。</span><span class="sxs-lookup"><span data-stu-id="53db6-164">Select the **Signature** option.</span></span>|  
    |<span data-ttu-id="53db6-165">**キーのオプション**</span><span class="sxs-lookup"><span data-stu-id="53db6-165">**Additional Key Options**</span></span>|<span data-ttu-id="53db6-166">次のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="53db6-166">Place a check in the following options:</span></span><br /><br /> <span data-ttu-id="53db6-167">-   **キー エクスポート可能としてマークします。**</span><span class="sxs-lookup"><span data-stu-id="53db6-167">-   **Mark keys as exportable**</span></span><br /><span data-ttu-id="53db6-168">-   **ローカル コンピューター証明書ストアに証明書を保存します。**</span><span class="sxs-lookup"><span data-stu-id="53db6-168">-   **Store certificate in the local computer certificate store**</span></span>|  
    |<span data-ttu-id="53db6-169">**表示名**</span><span class="sxs-lookup"><span data-stu-id="53db6-169">**Friendly Name**</span></span>|<span data-ttu-id="53db6-170">型**Fabrikam Signature**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-170">Type **Fabrikam Signature**.</span></span>|  
  
6.  <span data-ttu-id="53db6-171">をクリックして**送信**、順にクリック**はい**証明書を要求するように求められたらです。</span><span class="sxs-lookup"><span data-stu-id="53db6-171">Click **Submit**, and then click **Yes** when asked to request the certificate.</span></span>  
  
7.  <span data-ttu-id="53db6-172">**証明書は発行**] ページで [**この証明書をインストール**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-172">On the **Certificate Issued** page, click **Install this certificate**.</span></span>  
  
8.  <span data-ttu-id="53db6-173">手順 1. ~ 7. で情報を変更する、**名前**ボックスに、**識別情報**セクションおよび**フレンドリ名**ボックス**Contoso署名**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-173">Repeat steps 1-7, changing the information in the **Name** box in the **Identifying Information** section and the **Friendly Name** box to **Contoso Signature**.</span></span>  
  
### <a name="to-generate-private-certificates-for-the-encryption-and-signature-certificates"></a><span data-ttu-id="53db6-174">暗号化証明書および署名証明書のプライベート証明書を生成するには</span><span class="sxs-lookup"><span data-stu-id="53db6-174">To generate private certificates for the Encryption and Signature certificates</span></span>  
  
1.  <span data-ttu-id="53db6-175">をクリックして**開始**、 をクリックして**実行**、型**MMC**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-175">Click **Start**, click **Run**, type **MMC**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="53db6-176">コンソール 1 ウィンドウで、上、**ファイル** メニューのをクリックして**スナップインの追加と削除**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-176">In the Console1 window, on the **File** menu, click **Add/Remove Snap-in**.</span></span>  
  
3.  <span data-ttu-id="53db6-177">スナップインの追加と削除 ダイアログ ボックスで、上、**スタンドアロン** タブで、をクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-177">In the Add/Remove Snap-in dialog box, on the **Standalone** tab, click **Add**.</span></span>  
  
4.  <span data-ttu-id="53db6-178">スタンドアロン スナップインの追加 ダイアログ ボックスで、選択、**証明書**スナップインから、**利用できるスタンドアロン スナップイン**一覧をクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-178">In the Add Standalone Snap-in dialog box, select the **Certificates** snap-in from the **Available Standalone Snap-ins** list, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="53db6-179">証明書スナップイン] ダイアログ ボックスで選択 **[ユーザー アカウント**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-179">In the Certificates snap-in dialog box, select **My user account**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="53db6-180">コンピューターの選択] ダイアログ ボックス [**完了**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-180">In the Select Computer dialog box, click **Finish**.</span></span>  
  
7.  <span data-ttu-id="53db6-181">[スタンドアロン スナップインの追加] ダイアログ ボックスで、**閉じる**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-181">In the Add Standalone Snap-in dialog box, click **Close**.</span></span>  
  
8.  <span data-ttu-id="53db6-182">[スナップインの追加と削除] ダイアログ ボックスで、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-182">In the Add/Remove Snap-in dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="53db6-183">コンソール 1 ウィンドウで **証明書 (ローカル コンピューター)**、展開**個人**、順にクリック**証明書**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-183">In the Console1 window, expand **Certificates (Local Computer)**, expand **Personal**, and then click **Certificates**.</span></span>  
  
10. <span data-ttu-id="53db6-184">右側のペインで右クリックし、 **Fabrikam Encryption**をポイントし、証明書の**すべてのタスク**、クリックして**エクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-184">In the right pane, right-click the **Fabrikam Encryption** certificate, point to **All Tasks**, and then click **Export**.</span></span>  
  
11. <span data-ttu-id="53db6-185">**証明書のエクスポート ウィザードへようこそ** ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-185">On the **Welcome to the Certificate Export Wizard** page, click **Next**.</span></span>  
  
12. <span data-ttu-id="53db6-186">**秘密キーのエクスポート** ページで、 **はい、秘密キーをエクスポート**、順にクリック**次**。</span><span class="sxs-lookup"><span data-stu-id="53db6-186">On the **Export Private Key** page, select **Yes, export the private key**, and then click **Next**.</span></span>  
  
13. <span data-ttu-id="53db6-187">**エクスポート ファイルの形式**ことを確認 ページで、 **Personal Information Exchange**唯一のオプションを選択するは、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-187">On the **Export File Format** page, make sure that **Personal Information Exchange** is the only option selected, and then click **Next**.</span></span>  
  
14. <span data-ttu-id="53db6-188">**パスワード**] ページの [、**パスワード**と**パスワードの確認**ボックスに「 **mysecret**、クリックしてして **[次へ]**.</span><span class="sxs-lookup"><span data-stu-id="53db6-188">On the **Password** page, in the **Password** and **Confirm Password** boxes, type **mysecret**, and then click **Next**.</span></span>  
  
15. <span data-ttu-id="53db6-189">**ファイルにエクスポート**] ページで [**参照**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-189">On the **File To Export** page, click **Browse**.</span></span>  
  
16. <span data-ttu-id="53db6-190">**名前を付けて保存**ファイル パスを使用して証明書を保存 ダイアログ ボックス、 *\<ドライブ\>*: \Certs\Fabrikam Private Encryption.pfx です。</span><span class="sxs-lookup"><span data-stu-id="53db6-190">In the **Save As** dialog box, save the certificate using the file path *\<drive\>*:\Certs\Fabrikam Private Encryption.pfx.</span></span>  
  
17. <span data-ttu-id="53db6-191">**エクスポートするファイル**] ページで [**次**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-191">On the **File to Export** page, click **Next**.</span></span>  
  
18. <span data-ttu-id="53db6-192">**証明書のエクスポート ウィザードの完了**] ページで [**完了**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-192">On the **Completing the Certificate Export Wizard** page, click **Finish**.</span></span>  
  
19. <span data-ttu-id="53db6-193">エクスポートを成功を示すポップアップで証明書のエクスポート ウィザード、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-193">In the Certificate Export Wizard popup indicating a successful export, click **OK**.</span></span>  
  
20. <span data-ttu-id="53db6-194">Fabrikam 署名証明書を生成するため、ファイル名 Fabrikam Private Signature.pfx を使用して、手順 10. ～ 19. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="53db6-194">Repeat steps 10-19 for the Fabrikam Signature certificate using the file name Fabrikam Private Signature.pfx.</span></span>  
  
21. <span data-ttu-id="53db6-195">Contoso 署名証明書および Contoso 暗号化証明書を生成するため、それぞれファイル名 Contoso Private Signature.pfx と Contoso Private Encryption.pfx を使用して、手順 10. ～ 19. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="53db6-195">Repeat steps 10-19 for the Contoso Signature and Contoso Encryption certificates using the file names Contoso Private Signature.pfx and Contoso Private Encryption.pfx, respectively.</span></span>  
  
### <a name="to-generate-public-certificates-for-the-encryption-and-signature-certificates"></a><span data-ttu-id="53db6-196">暗号化証明書および署名証明書のパブリック証明書を生成するには</span><span class="sxs-lookup"><span data-stu-id="53db6-196">To generate public certificates for the Encryption and Signature certificates</span></span>  
  
1.  <span data-ttu-id="53db6-197">コンソール 1 ウィンドウで、**証明書-現在のユーザー**、展開**個人**をクリックし、**証明書**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-197">In the Console1 window, expand **Certificates – Current User**, expand **Personal**, and then click **Certificates**.</span></span>  
  
2.  <span data-ttu-id="53db6-198">右クリックし、 **Fabrikam Encryption**をポイントし、証明書の**すべてのタスク**、クリックして**エクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-198">Right-click the **Fabrikam Encryption** certificate, point to **All Tasks**, and then click **Export**.</span></span>  
  
3.  <span data-ttu-id="53db6-199">**証明書のエクスポート ウィザードへようこそ** ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-199">On the **Welcome to the Certificate Export Wizard** page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="53db6-200">**秘密キーのエクスポート**] ページで、[**いいえ、秘密キーをエクスポートしません**、クリックして **[次へ]** です。</span><span class="sxs-lookup"><span data-stu-id="53db6-200">On the **Export Private Key** page, select **No, do not export the private key**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="53db6-201">**エクスポート ファイルの形式**] ページで [**次**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-201">On the **Export File Format** page, click **Next**.</span></span>  
  
6.  <span data-ttu-id="53db6-202">**ファイルにエクスポート**] ページで [**参照**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-202">On the **File To Export** page, click **Browse**.</span></span>  
  
7.  <span data-ttu-id="53db6-203">名前を付けて保存 ダイアログ ボックスで、入力**\<ドライブ\>: \Certs**の**で保存**、 **Fabrikam Public Encryption.cer**として**ファイル名**、および **\*.cer**の**型として保存**、順にクリック**保存**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-203">In the Save As dialog box, enter **\<drive\>:\Certs** for **Save in**, **Fabrikam Public Encryption.cer** as **File name**, and **\*.cer** for **Save as type**, and then click **Save**.</span></span>  
  
8.  <span data-ttu-id="53db6-204">**エクスポートするファイル**] ページで [**次**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-204">On the **File to Export** page, click **Next**.</span></span>  
  
9. <span data-ttu-id="53db6-205">**証明書のエクスポート ウィザードの完了**] ページで [**完了**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-205">On the **Completing the Certificate Export Wizard** page, click **Finish**.</span></span>  
  
10. <span data-ttu-id="53db6-206">エクスポートを成功を示すポップアップで証明書のエクスポート ウィザード、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="53db6-206">In the Certificate Export Wizard popup indicating a successful export, click **OK**.</span></span>  
  
11. <span data-ttu-id="53db6-207">Fabrikam 署名証明書を生成するため、ファイル名 Fabrikam Public Signature.cer を使用して、手順 1. ～ 9. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="53db6-207">Repeat steps 1-9 for the Fabrikam Signature certificate using the file name Fabrikam Public Signature.cer.</span></span>  
  
12. <span data-ttu-id="53db6-208">Contoso 署名証明書および Contoso 暗号化証明書を生成するため、それぞれファイル名 Contoso Public Signature.cer と Contoso Public Encryption.cer を使用して、手順 1. ～ 9. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="53db6-208">Repeat steps 1-9 for the Contoso Signature and Contoso Encryption certificates using the file names Contoso Public Signature.cer and Contoso Public Encryption.cer, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53db6-209">参照</span><span class="sxs-lookup"><span data-stu-id="53db6-209">See Also</span></span>  
 [<span data-ttu-id="53db6-210">手順 3: パブリック証明書とプライベート証明書のインポート</span><span class="sxs-lookup"><span data-stu-id="53db6-210">Step 3: Importing Public and Private Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-importing-public-and-private-certificates.md)