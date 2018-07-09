---
title: '手順 4: セキュリティで保護を有効にする IIS のレイヤーをソケット |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Secure Socket Layers
- IIS
- double action tutorial, enabling SSL in IIS
- SSL
ms.assetid: 96109294-595a-46ac-974e-33123df79ed5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be53660b5632450d8fa8cb38480c9b728d460bad
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009163"
---
# <a name="step-4-enabling-secure-sockets-layer-in-iis"></a><span data-ttu-id="cd8ab-102">手順 4: IIS でレイヤーをソケット セキュリティで保護を有効にします。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-102">Step 4: Enabling Secure Sockets Layer in IIS</span></span>
<span data-ttu-id="cd8ab-103">SSL (Secure Sockets Layer) は、クライアントとサーバーとの間の通信チャネルをセキュリティで保護するためのプロトコルです。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-103">Secure Sockets Layer (SSL) is a protocol designed to secure the communication channel between a client and a server.</span></span> <span data-ttu-id="cd8ab-104">Contoso 組織と Fabrikam 組織は、Microsoft® インターネット インフォメーション サービス (IIS) 7.5 または 7.0 で SSL を有効にすることにより、すべてのデータ転送に認証と暗号化を使用して通信を行います。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-104">By enabling SSL in Microsoft® Internet Information Services (IIS) 7.5/7.0, the Contoso and Fabrikam organizations communicate using authentication and encryption for all data transfers.</span></span> <span data-ttu-id="cd8ab-105">ここでは、IIS 7.5 または 7.0 で SSL を有効にする手順について学びます。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-105">In this step, you learn how to enable SSL in IIS 7.5/7.0.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cd8ab-106">Contoso のコンピューターと Fabrikam のコンピューターの両方でこの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-106">You have to perform this step on both the Contoso and Fabrikam computers.</span></span>  
  
### <a name="to-prepare-a-new-server-certificate"></a><span data-ttu-id="cd8ab-107">新しいサーバー証明書を準備するには</span><span class="sxs-lookup"><span data-stu-id="cd8ab-107">To prepare a new server certificate</span></span>  
  
1. <span data-ttu-id="cd8ab-108">クリックして**開始**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-108">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2. <span data-ttu-id="cd8ab-109">インターネット インフォメーション サービスの左側のウィンドウで  **\<** <em>computer_name</em> **\>** (*ローカル コンピューター*)、展開**Websites**を右クリックして**既定の Web サイト**、順にクリックします**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-109">In the Internet Information Services left pane, expand **\<**<em>computer_name</em>**\>** (*local computer*), expand **Web Sites**, right-click **Default Web Site**, and then click **Properties**.</span></span>  
  
3. <span data-ttu-id="cd8ab-110">既定の Web サイト ダイアログ ボックスで、上、**ディレクトリ セキュリティ** タブで **サーバー証明書**を開始する、 **IIS 証明書ウィザード**。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-110">In the Default Web Sites dialog box, on the **Directory Security** tab, click **Server Certificate** to start the **IIS Certificate Wizard**.</span></span>  
  
4. <span data-ttu-id="cd8ab-111">**Web サーバー証明書ウィザードへようこそ**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-111">On the **Welcome to the Web Server Certificate Wizard** page, click **Next**.</span></span>  
  
5. <span data-ttu-id="cd8ab-112">**サーバー証明書**] ページで、[**新しい証明書を作成**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-112">On the **Server Certificate** page, select **Create a new certificate**, and then click **Next**.</span></span>  
  
6. <span data-ttu-id="cd8ab-113">**証明書の要求**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-113">On the **Delayed or immediate request** page, click **Next**.</span></span>  
  
7. <span data-ttu-id="cd8ab-114">**名およびセキュリティの設定**] ページで [ **[次へ]**、既定値を保持します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-114">On the **Name and Security Settings** page, click **Next**, keeping the defaults.</span></span>  
  
8. <span data-ttu-id="cd8ab-115">**組織情報**ページで、**組織**ボックスに「 **Contoso** Contoso のコンピューター上にある場合または**Fabrikam**上にある場合、Fabrikam のコンピューターで、**組織単位**ボックスに「**テスト**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-115">On the **Organization Information** page, in the **Organization** box, type **Contoso** if on the Contoso computer or **Fabrikam** if on the Fabrikam computer, in the **Organizational unit** box, type **Test**, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="cd8ab-116">**サイトの一般名**] ページの [、**共通名**ボックスで、コンピューターの名前を入力し、クリックして **[次へ]** します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-116">On the **Your Site's Common Name** page, in the **Common name** box, type the name of your computer, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="cd8ab-117">**地理情報**] ページの [、**都道府県**ボックスで、都道府県を入力、**市区町村**ボックスで、/地域、市区町村を入力し、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-117">On the **Geographical Information** page, in the **State/province** box, type your state/province, in the **City/locality** box, type your city/locality, and then click **Next**.</span></span>  
  
11. <span data-ttu-id="cd8ab-118">**証明書要求ファイル名**] ページの [、**ファイル名**ボックスで、既定値のままに**C:\certreq.txt**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-118">On the **Certificate Request File Name** page, in the **File name** box, leave the default **C:\certreq.txt**, and then click **Next**.</span></span>  
  
12. <span data-ttu-id="cd8ab-119">**要求ファイルの概要**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-119">On the **Request File Summary** page, click **Next**.</span></span>  
  
13. <span data-ttu-id="cd8ab-120">**Web サーバー証明書ウィザードの完了**] ページで [**完了**を閉じる、 **IIS 証明書ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-120">On the **Completing the Web Server Certificate Wizard** page, click **Finish** to close the **IIS Certificate Wizard**.</span></span>  
  
### <a name="to-generate-a-new-server-certificate"></a><span data-ttu-id="cd8ab-121">新しいサーバー証明書を生成するには</span><span class="sxs-lookup"><span data-stu-id="cd8ab-121">To generate a new server certificate</span></span>  
  
1.  <span data-ttu-id="cd8ab-122">Internet Explorer で、検索し、開きます http://\<*contoso_machine*\>/CertSrv します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-122">In Internet Explorer, locate and open http://\<*contoso_machine*\>/CertSrv.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cd8ab-123">手順 1 で、開く http://\<*contoso_machine*\>/CertSrv Contoso または Fabrikam のコンピューターにします。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-123">In step 1, open http://\<*contoso_machine*\>/CertSrv on the Contoso or Fabrikam computer.</span></span>  
  
2.  <span data-ttu-id="cd8ab-124">**Microsoft 証明書サービス ウィザードへようこそ**] ページで [**証明書を要求します。**</span><span class="sxs-lookup"><span data-stu-id="cd8ab-124">On the **Microsoft Certificate Services Wizard Welcome** page, click **Request a certificate.**</span></span>  
  
3.  <span data-ttu-id="cd8ab-125">**証明書を要求**] ページで [**高度な証明書の要求**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-125">On the **Request a Certificate** page, click **advanced certificate request**.</span></span>  
  
4.  <span data-ttu-id="cd8ab-126">**証明書要求の高度な**] ページで [ **base 64 エンコード CMC または PKCS #10 ファイルを使用して証明書の要求を送信するか、または base 64 エンコード PKCS #7 ファイルを使用して、更新要求を送信する**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-126">On the **Advanced Certificate Request** page, click **Submit a certificate request by using a base-64-encoded CMC or PKCS #10 file, or submit a renewal request by using a base-64-encoded PKCS #7 file**.</span></span>  
  
5.  <span data-ttu-id="cd8ab-127">**証明書の要求または更新要求を送信**] ページで [**ファイルを挿入する参照**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-127">On the **Submit a Certificate Request or Renewal Request** page, click **Browse for a file to insert**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cd8ab-128">メモ帳または別のテキスト エディターでファイル C:\certreq.txt を開き、リンクをクリックすると、セキュリティ エラーが発生した場合、ファイルの内容をコピーおよびでその情報を貼り付けて、**保存された要求**ボックスをクリックして**送信**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-128">If you receive a security error when clicking the link, open the file C:\certreq.txt in Notepad or another text editor, copy the contents of the file and paste that information in the **Saved Request** box, and then click **Submit**.</span></span> <span data-ttu-id="cd8ab-129">これで、手順 10. に進めます。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-129">You can then go to step 10.</span></span>  
  
6.  <span data-ttu-id="cd8ab-130">をクリックして**参照**を開く、 **Choose File**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-130">Click **Browse** to open the **Choose File** dialog box.</span></span>  
  
7.  <span data-ttu-id="cd8ab-131">**ファイルの選択** ダイアログ ボックスで、検索、 *\<ドライブ\>*: \ フォルダー、certreq.txt ファイルを選択し、順にクリックします**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-131">In the **Choose File** dialog box, locate the *\<drive\>*:\ folder, select the certreq.txt file, and then click **Open**.</span></span>  
  
8.  <span data-ttu-id="cd8ab-132">**証明書の要求または更新要求を送信**] ページで [**読み取り**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-132">On the **Submit a Certificate Request or Renewal Request** page, click **Read**.</span></span>  
  
9. <span data-ttu-id="cd8ab-133">**証明書の要求または更新要求を送信**] ページで [**送信**新しい証明書を生成します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-133">On the **Submit a Certificate Request or Renewal Request** page, click **Submit** to generate the new certificate.</span></span>  
  
10. <span data-ttu-id="cd8ab-134">**証明書は発行**] ページで [**証明書のダウンロード**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-134">On the **Certificate Issued** page, click **Download Certificate**.</span></span>  
  
11. <span data-ttu-id="cd8ab-135">**ファイルのダウンロード**ダイアログ ボックスで、をクリックして**保存**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-135">In the **File Download** dialog box, click **Save**.</span></span>  
  
12. <span data-ttu-id="cd8ab-136">**付けて** ダイアログ ボックスで、証明書を保存\<ドライブ\>: \Certs\SSLCert.cer をクリック**保存**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-136">In the **Save As** dialog box, save the certificate to \<drive\>:\Certs\SSLCert.cer, and then click **Save**.</span></span>  
  
13. <span data-ttu-id="cd8ab-137">クリックして**閉じます**を閉じる、**ダウンロードの完了** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-137">Click **Close** to close the **Download Complete** dialog box.</span></span>  
  
### <a name="to-prepare-a-new-server-certificate-for-iis"></a><span data-ttu-id="cd8ab-138">IIS で新しいサーバー証明書を準備するには</span><span class="sxs-lookup"><span data-stu-id="cd8ab-138">To Prepare a new Server Certificate for IIS</span></span>  
  
1.  <span data-ttu-id="cd8ab-139">クリックして**開始**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-139">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="cd8ab-140">インターネット インフォメーション サービスの左側のウィンドウで < computer_name > (ローカル コンピューター) をクリックして、ダブルクリック**サーバー証明書**右側のペインでします。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-140">In the Internet Information Services left pane, click <computer_name> (local computer), double click **Server Certificates** in the right pane.</span></span> <span data-ttu-id="cd8ab-141">選択**証明書の要求の作成**操作 ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-141">Select **Create Certificate Request** from Actions pane.</span></span>  
  
3.  <span data-ttu-id="cd8ab-142">識別名のプロパティ ダイアログ ボックスで、一般的な名前でコンピューターの名前を入力します組織内のテキスト ボックス: ボックスに「 **Contoso** Contoso のコンピューター上にある場合または**Fabrikam** Fabrikam 上にある場合。組織単位内のコンピューター: ボックスに「市区町村 ボックスで、テスト、都道府県ボックスに市区町村、、国/地域ドロップダウンを選択、国/地域都道府県を入力およびクリック**次へ**.</span><span class="sxs-lookup"><span data-stu-id="cd8ab-142">In Distinguished Name Properties dialog box type the name of the computer in the Common name: text box, in the Organization: box, type **Contoso** if on the Contoso computer or **Fabrikam** if on the Fabrikam computer, in the Organizational unit: box type Test, in the City/locality box, type your city/locality, in the State/province box, type your state/province, in the Country/region drop down, select your Country/region and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="cd8ab-143">暗号化サービス プロバイダーのプロパティ] ダイアログ ボックスで、[**次**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-143">In the Cryptographic Service Provider Properties dialog box, click **Next**.</span></span>  
  
5.  <span data-ttu-id="cd8ab-144">ファイル名 ダイアログ ボックスで、テキスト ボックスで C:\certreq.txt を指定する をクリックして**完了**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-144">In the File Name dialog box, specify C:\certreq.txt in the text box, click **Finish**.</span></span>  
  
### <a name="to-generate-a-new-server-certificate-for-iis"></a><span data-ttu-id="cd8ab-145">IIS で新しいサーバー証明書を生成するには</span><span class="sxs-lookup"><span data-stu-id="cd8ab-145">To generate a new server certificate for IIS</span></span>  
  
1.  <span data-ttu-id="cd8ab-146">Internet Explorer を http://<contoso_machine>/CertSrv を開きます。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-146">In Internet Explorer, locate and open http://<contoso_machine>/CertSrv.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cd8ab-147">手順 1 で、Contoso または Fabrikam のコンピューター上の http://<contoso_machine>/CertSrv を開きます。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-147">In step 1, open http://<contoso_machine>/CertSrv on the Contoso or Fabrikam computer.</span></span>  
  
2.  <span data-ttu-id="cd8ab-148">Microsoft 証明書サービス ウィザードへようこそ ページで、**証明書を要求**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-148">On the Microsoft Certificate Services Wizard Welcome page, click **Request a certificate**.</span></span>  
  
3.  <span data-ttu-id="cd8ab-149">要求の証明書 ページで、をクリックして**証明書の要求の高度な**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-149">On the Request a Certificate page, click **Advanced Certificate Request**.</span></span>  
  
4.  <span data-ttu-id="cd8ab-150">証明書要求の詳細設定 ページで、次のようにクリックします。**証明書の要求を送信**で base 64 エンコード CMC または PKCS #10 ファイルを使用して、または base 64 エンコード PKCS #7 ファイルを使用して、更新要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-150">On the Advanced Certificate Request page, click **Submit a certificate request** by using a base-64-encoded CMC or PKCS #10 file, or submit a renewal request by using a base-64-encoded PKCS #7 file.</span></span>  
  
5.  <span data-ttu-id="cd8ab-151">メモ帳または別のテキスト エディターでファイル C:\certreq.txt を開き、ファイルの内容をコピーおよび貼り付け、**保存された要求**ボックス証明書の要求または更新要求のページでは、送信、をクリックして**送信**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-151">Open the file C:\certreq.txt in Notepad or another text editor, copy the contents of the file and paste that information in the **Saved Request** box on the Submit a Certificate Request or Renewal Request page, and then click **Submit**.</span></span>  
  
6.  <span data-ttu-id="cd8ab-152">証明書の発行 ページで、**証明書のダウンロード**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-152">On the Certificate Issued page, click **Download Certificate**.</span></span>  
  
7.  <span data-ttu-id="cd8ab-153">ファイルのダウンロード] ダイアログ ボックスで、[**保存**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-153">In the File Download dialog box, click **Save**.</span></span>  
  
8.  <span data-ttu-id="cd8ab-154">名前を付けて保存 ダイアログ ボックスで、保存する証明書を\<ドライブ\>: \Certs\SSLCert.cer をクリック**保存**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-154">In the Save As dialog box, save the certificate to \<drive\>:\Certs\SSLCert.cer, and then click **Save**.</span></span>  
  
### <a name="to-import-the-server-certificate-into-iis"></a><span data-ttu-id="cd8ab-155">サーバー証明書を IIS にインポートするには</span><span class="sxs-lookup"><span data-stu-id="cd8ab-155">To import the server certificate into IIS</span></span>  
  
1.  <span data-ttu-id="cd8ab-156">クリックして**開始**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-156">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="cd8ab-157">インターネット インフォメーション サービスの左側のウィンドウで次のようにクリックします。 **(ローカル コンピューター)**、ダブルクリック**サーバー証明書**右側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-157">In the Internet Information Services left pane, click **(local computer)**, double click **Server Certificates** in the right pane.</span></span> <span data-ttu-id="cd8ab-158">選択**証明書要求の完全な**[操作] ウィンドウから。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-158">Select **Complete Certificate Request** from the Actions pane.</span></span>  
  
3.  <span data-ttu-id="cd8ab-159">証明機関の応答の指定 ダイアログ ボックスに「 **\<ドライブ\>: \Certs\SSLCert.cer**で**証明機関から応答を格納するファイル名**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-159">In Specify Certificate Authority Response dialog box type **\<drive\>:\Certs\SSLCert.cer** in **File name containing the certification authority’s response** text box.</span></span> <span data-ttu-id="cd8ab-160">フレンドリ名テキスト ボックスに「 **ContosoSSLCert**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-160">In Friendly name text box type **ContosoSSLCert**.</span></span>  
  
### <a name="to-enable-ssl-bindings-for-iis"></a><span data-ttu-id="cd8ab-161">IIS で SSL バインドを有効にするには</span><span class="sxs-lookup"><span data-stu-id="cd8ab-161">To enable SSL bindings for IIS</span></span>  
  
1.  <span data-ttu-id="cd8ab-162">クリックして**開始**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-162">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="cd8ab-163">インターネット インフォメーション サービスの左側のウィンドウで  **(ローカル コンピューター)**、展開**サイト**、右クリックして**既定の Web サイト**、順にクリックします**編集バインド**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-163">In the Internet Information Services left pane, expand **(local computer)**, expand **Sites**, right-click **Default Web Site**, and then click **Edit Bindings**.</span></span>  
  
3.  <span data-ttu-id="cd8ab-164">[サイト バインド] ダイアログ ボックス**追加**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-164">In Site Bindings dialog box click **Add**.</span></span> <span data-ttu-id="cd8ab-165">サイト バインドの追加 ダイアログ ボックスで、次のように選択します**https**型ドロップダウンから、次のように選択します。 **ContosoSSLCert** SSL 証明書ドロップダウンから、次のようにクリックします。 **OK**、 をクリック**閉じる。**.</span><span class="sxs-lookup"><span data-stu-id="cd8ab-165">In the Add Site Binding dialog box select **https** from Type drop down, select **ContosoSSLCert** from SSL certificate drop down, click **OK**, click **Close**.</span></span>  
  
### <a name="to-import-the-server-certificate-into-iis"></a><span data-ttu-id="cd8ab-166">サーバー証明書を IIS にインポートするには</span><span class="sxs-lookup"><span data-stu-id="cd8ab-166">To import the server certificate into IIS</span></span>  
  
1. <span data-ttu-id="cd8ab-167">クリックして**開始**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-167">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2. <span data-ttu-id="cd8ab-168">インターネット インフォメーション サービスの左側のウィンドウで [ **\<** <em>computer_name</em> \> (*ローカル コンピューター*)、展開**Webサイト**、右クリック**既定の Web サイト**、] をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-168">In the Internet Information Services left pane, expand **\<**<em>computer_name</em>\> (*local computer*), expand **Web Sites**, right-click **Default Web Site**, and then click **Properties**.</span></span>  
  
3. <span data-ttu-id="cd8ab-169">既定の Web サイトのプロパティ ダイアログ ボックスで、**ディレクトリ セキュリティ** タブで **サーバー証明書**を開始する、 **IIS 証明書ウィザード**。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-169">In the Default Web Site Properties dialog box, on the **Directory Security** tab, click **Server Certificate** to start the **IIS Certificate Wizard**.</span></span>  
  
4. <span data-ttu-id="cd8ab-170">**Web サーバー証明書ウィザードへようこそ**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-170">On the **Welcome to the Web Server Certificate Wizard** page, click **Next**.</span></span>  
  
5. <span data-ttu-id="cd8ab-171">**保留中の証明書要求**] ページで、[**保留中の要求を処理し、証明書をインストール**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-171">On the **Pending Certificate Request** page, select **Process the pending request and install the certificate**, and then click **Next**.</span></span>  
  
6. <span data-ttu-id="cd8ab-172">**保留中の要求を処理**ページで、**パスとファイル名**ボックスに「 **\<ドライブ\>: \Certs\SSLCert.cer** (またはそのファイルを参照)クリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-172">On the **Process a Pending Request** page, in the **Path and file name** box, type **\<drive\>:\Certs\SSLCert.cer** (or browse to that file) and then click **Next**.</span></span>  
  
7. <span data-ttu-id="cd8ab-173">**SSL ポート ページ**、 をクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-173">On the **SSL Port page**, click **Next**.</span></span>  
  
8. <span data-ttu-id="cd8ab-174">**証明書の概要**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-174">On the **Certificate Summary** page, click **Next**.</span></span>  
  
9. <span data-ttu-id="cd8ab-175">**Web サーバー証明書ウィザードの完了**] ページで [**完了**します。</span><span class="sxs-lookup"><span data-stu-id="cd8ab-175">On the **Completing the Web Server Certificate Wizard** page, click **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd8ab-176">参照</span><span class="sxs-lookup"><span data-stu-id="cd8ab-176">See Also</span></span>  
 [<span data-ttu-id="cd8ab-177">Contoso ソリューションの作成と構成</span><span class="sxs-lookup"><span data-stu-id="cd8ab-177">Creating and Configuring the Contoso Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-the-contoso-solution.md)