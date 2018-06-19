---
title: '手順 4: IIS でレイヤーをソケット セキュリティで保護の有効化 |Microsoft ドキュメント'
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
ms.openlocfilehash: 2964b6ac26d6685a1c38b88c5bbf98e8119f3502
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967000"
---
# <a name="step-4-enabling-secure-sockets-layer-in-iis"></a><span data-ttu-id="7602d-102">手順 4: IIS でレイヤーをソケット セキュリティで保護を有効にします。</span><span class="sxs-lookup"><span data-stu-id="7602d-102">Step 4: Enabling Secure Sockets Layer in IIS</span></span>
<span data-ttu-id="7602d-103">SSL (Secure Sockets Layer) は、クライアントとサーバーとの間の通信チャネルをセキュリティで保護するためのプロトコルです。</span><span class="sxs-lookup"><span data-stu-id="7602d-103">Secure Sockets Layer (SSL) is a protocol designed to secure the communication channel between a client and a server.</span></span> <span data-ttu-id="7602d-104">Contoso 組織と Fabrikam 組織は、Microsoft® インターネット インフォメーション サービス (IIS) 7.5 または 7.0 で SSL を有効にすることにより、すべてのデータ転送に認証と暗号化を使用して通信を行います。</span><span class="sxs-lookup"><span data-stu-id="7602d-104">By enabling SSL in Microsoft® Internet Information Services (IIS) 7.5/7.0, the Contoso and Fabrikam organizations communicate using authentication and encryption for all data transfers.</span></span> <span data-ttu-id="7602d-105">ここでは、IIS 7.5 または 7.0 で SSL を有効にする手順について学びます。</span><span class="sxs-lookup"><span data-stu-id="7602d-105">In this step, you learn how to enable SSL in IIS 7.5/7.0.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7602d-106">Contoso のコンピューターと Fabrikam のコンピューターの両方でこの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7602d-106">You have to perform this step on both the Contoso and Fabrikam computers.</span></span>  
  
### <a name="to-prepare-a-new-server-certificate"></a><span data-ttu-id="7602d-107">新しいサーバー証明書を準備するには</span><span class="sxs-lookup"><span data-stu-id="7602d-107">To prepare a new server certificate</span></span>  
  
1.  <span data-ttu-id="7602d-108">をクリックして**開始**、 をポイント**管理ツール**、順にクリック**インターネット インフォメーション サービス (IIS) マネージャー**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-108">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="7602d-109">インターネット インフォメーション サービスの左ペインで、展開 **\<**  *computer_name*  **\>**  (*ローカル コンピューター*)、展開**Web サイト**を右クリックして**既定の Web サイト**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-109">In the Internet Information Services left pane, expand **\<***computer_name***\>** (*local computer*), expand **Web Sites**, right-click **Default Web Site**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="7602d-110">既定の Web サイト ダイアログ ボックスで、**ディレクトリ セキュリティ** タブで、をクリックして**サーバー証明書**を開始する、 **IIS 証明書ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-110">In the Default Web Sites dialog box, on the **Directory Security** tab, click **Server Certificate** to start the **IIS Certificate Wizard**.</span></span>  
  
4.  <span data-ttu-id="7602d-111">**Web サーバー証明書ウィザードへようこそ** ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-111">On the **Welcome to the Web Server Certificate Wizard** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="7602d-112">**サーバー証明書**] ページで、[**新しい証明書を作成**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-112">On the **Server Certificate** page, select **Create a new certificate**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="7602d-113">**証明書の要求**] ページで [**次**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-113">On the **Delayed or immediate request** page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="7602d-114">**名とセキュリティ設定** ページで、をクリックして**次へ**、既定値を保持します。</span><span class="sxs-lookup"><span data-stu-id="7602d-114">On the **Name and Security Settings** page, click **Next**, keeping the defaults.</span></span>  
  
8.  <span data-ttu-id="7602d-115">**組織情報**] ページの [、**組織**ボックスに、入力**Contoso** Contoso のコンピューター上にある場合または**Fabrikam**上にある場合、Fabrikam のコンピューターで、**組織単位**ボックスに、入力**テスト**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-115">On the **Organization Information** page, in the **Organization** box, type **Contoso** if on the Contoso computer or **Fabrikam** if on the Fabrikam computer, in the **Organizational unit** box, type **Test**, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="7602d-116">**サイトの一般名**] ページの [、**共通名**ボックスで、コンピューターの名前を入力し、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-116">On the **Your Site's Common Name** page, in the **Common name** box, type the name of your computer, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="7602d-117">**地理情報**] ページの [、**都道府県/州**ボックスで、都道府県を入力、**市区町村**ボックスに市区町村を入力し、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-117">On the **Geographical Information** page, in the **State/province** box, type your state/province, in the **City/locality** box, type your city/locality, and then click **Next**.</span></span>  
  
11. <span data-ttu-id="7602d-118">**証明書要求ファイル名**] ページの [、**ファイル名**ボックスで、既定値のままに**C:\certreq.txt**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-118">On the **Certificate Request File Name** page, in the **File name** box, leave the default **C:\certreq.txt**, and then click **Next**.</span></span>  
  
12. <span data-ttu-id="7602d-119">**要求ファイルの概要**] ページで [**次**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-119">On the **Request File Summary** page, click **Next**.</span></span>  
  
13. <span data-ttu-id="7602d-120">**Web サーバー証明書ウィザードの完了** ページで、をクリックして**完了**を閉じる、 **IIS 証明書ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-120">On the **Completing the Web Server Certificate Wizard** page, click **Finish** to close the **IIS Certificate Wizard**.</span></span>  
  
### <a name="to-generate-a-new-server-certificate"></a><span data-ttu-id="7602d-121">新しいサーバー証明書を生成するには</span><span class="sxs-lookup"><span data-stu-id="7602d-121">To generate a new server certificate</span></span>  
  
1.  <span data-ttu-id="7602d-122">Internet Explorer で見つけて開きます http://\<*contoso_machine*\>/CertSrv です。</span><span class="sxs-lookup"><span data-stu-id="7602d-122">In Internet Explorer, locate and open http://\<*contoso_machine*\>/CertSrv.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7602d-123">ステップ 1 で、開く http://\<*contoso_machine*\>Contoso または Fabrikam のコンピューター上の/CertSrv です。</span><span class="sxs-lookup"><span data-stu-id="7602d-123">In step 1, open http://\<*contoso_machine*\>/CertSrv on the Contoso or Fabrikam computer.</span></span>  
  
2.  <span data-ttu-id="7602d-124">**Microsoft 証明書サービス ウィザードへようこそ**] ページで [**証明書を要求します。**</span><span class="sxs-lookup"><span data-stu-id="7602d-124">On the **Microsoft Certificate Services Wizard Welcome** page, click **Request a certificate.**</span></span>  
  
3.  <span data-ttu-id="7602d-125">**証明書を要求**] ページで [**高度な証明書の要求**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-125">On the **Request a Certificate** page, click **advanced certificate request**.</span></span>  
  
4.  <span data-ttu-id="7602d-126">**証明書の要求の高度な**] ページで [ **base 64 エンコード CMC または PKCS #10 ファイルを使用して証明書の要求を送信または base 64 エンコード PKCS #7 ファイルを使用して、更新要求を送信**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-126">On the **Advanced Certificate Request** page, click **Submit a certificate request by using a base-64-encoded CMC or PKCS #10 file, or submit a renewal request by using a base-64-encoded PKCS #7 file**.</span></span>  
  
5.  <span data-ttu-id="7602d-127">**証明書の要求または更新要求を送信**] ページで [**を挿入するファイルの参照**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-127">On the **Submit a Certificate Request or Renewal Request** page, click **Browse for a file to insert**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7602d-128">メモ帳などのテキスト エディターでファイル C:\certreq.txt を開き、リンクをクリックすると、セキュリティ エラーが発生する場合、ファイルの内容をコピーしでその情報を貼り付けます、**保存された要求**ボックスをクリックして**送信**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-128">If you receive a security error when clicking the link, open the file C:\certreq.txt in Notepad or another text editor, copy the contents of the file and paste that information in the **Saved Request** box, and then click **Submit**.</span></span> <span data-ttu-id="7602d-129">これで、手順 10. に進めます。</span><span class="sxs-lookup"><span data-stu-id="7602d-129">You can then go to step 10.</span></span>  
  
6.  <span data-ttu-id="7602d-130">をクリックして**参照**を開くには、 **Choose File**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="7602d-130">Click **Browse** to open the **Choose File** dialog box.</span></span>  
  
7.  <span data-ttu-id="7602d-131">**Choose File**  ダイアログ ボックスで、検索、 *\<ドライブ\>*: \ フォルダーは、検索して certreq.txt ファイルを選択しをクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-131">In the **Choose File** dialog box, locate the *\<drive\>*:\ folder, select the certreq.txt file, and then click **Open**.</span></span>  
  
8.  <span data-ttu-id="7602d-132">**証明書の要求または更新要求を送信**] ページで [**読み取り**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-132">On the **Submit a Certificate Request or Renewal Request** page, click **Read**.</span></span>  
  
9. <span data-ttu-id="7602d-133">**証明書の要求または更新要求を送信** ページで、をクリックして**送信**を新しい証明書を生成します。</span><span class="sxs-lookup"><span data-stu-id="7602d-133">On the **Submit a Certificate Request or Renewal Request** page, click **Submit** to generate the new certificate.</span></span>  
  
10. <span data-ttu-id="7602d-134">**証明書は発行**] ページで [**証明書のダウンロード**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-134">On the **Certificate Issued** page, click **Download Certificate**.</span></span>  
  
11. <span data-ttu-id="7602d-135">**ファイルのダウンロード**ダイアログ ボックスで、をクリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-135">In the **File Download** dialog box, click **Save**.</span></span>  
  
12. <span data-ttu-id="7602d-136">**名前を付けて保存**ダイアログ ボックスで、証明書を保存、\<ドライブ\>: \Certs\SSLCert.cer をクリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-136">In the **Save As** dialog box, save the certificate to \<drive\>:\Certs\SSLCert.cer, and then click **Save**.</span></span>  
  
13. <span data-ttu-id="7602d-137">をクリックして**閉じる**を閉じる、**ダウンロードの完了** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="7602d-137">Click **Close** to close the **Download Complete** dialog box.</span></span>  
  
### <a name="to-prepare-a-new-server-certificate-for-iis"></a><span data-ttu-id="7602d-138">IIS で新しいサーバー証明書を準備するには</span><span class="sxs-lookup"><span data-stu-id="7602d-138">To Prepare a new Server Certificate for IIS</span></span>  
  
1.  <span data-ttu-id="7602d-139">をクリックして**開始**、 をポイント**管理ツール**、順にクリック**インターネット インフォメーション サービス (IIS) マネージャー**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-139">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="7602d-140">インターネット インフォメーション サービスの左ペインで [< computer_name > (ローカル コンピューター)] をクリックして、ダブルクリックして**サーバー証明書**右側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="7602d-140">In the Internet Information Services left pane, click <computer_name> (local computer), double click **Server Certificates** in the right pane.</span></span> <span data-ttu-id="7602d-141">選択**証明書の要求の作成**[操作] ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="7602d-141">Select **Create Certificate Request** from Actions pane.</span></span>  
  
3.  <span data-ttu-id="7602d-142">識別名のプロパティ ダイアログ ボックスで、一般的な名前でコンピューターの名前を入力します組織内のテキスト ボックス: ボックスに、入力**Contoso** Contoso のコンピューター上にある場合または**Fabrikam** Fabrikam 上にある場合。組織単位内のコンピューター: ボックスに「、市区町村 ボックスでテスト、市区町村、都道府県 ボックスに都道府県/州、国/地域ドロップダウンで、選択、国/地域と入力順にクリック**次へ**.</span><span class="sxs-lookup"><span data-stu-id="7602d-142">In Distinguished Name Properties dialog box type the name of the computer in the Common name: text box, in the Organization: box, type **Contoso** if on the Contoso computer or **Fabrikam** if on the Fabrikam computer, in the Organizational unit: box type Test, in the City/locality box, type your city/locality, in the State/province box, type your state/province, in the Country/region drop down, select your Country/region and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="7602d-143">[暗号化サービス プロバイダーのプロパティ] ダイアログ ボックスで、**次**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-143">In the Cryptographic Service Provider Properties dialog box, click **Next**.</span></span>  
  
5.  <span data-ttu-id="7602d-144">ファイル名 ダイアログ ボックスで、テキスト ボックスで C:\certreq.txt を指定 をクリックして**完了**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-144">In the File Name dialog box, specify C:\certreq.txt in the text box, click **Finish**.</span></span>  
  
### <a name="to-generate-a-new-server-certificate-for-iis"></a><span data-ttu-id="7602d-145">IIS で新しいサーバー証明書を生成するには</span><span class="sxs-lookup"><span data-stu-id="7602d-145">To generate a new server certificate for IIS</span></span>  
  
1.  <span data-ttu-id="7602d-146">Internet Explorer で、検索して http://<contoso_machine>/CertSrv を開きます。</span><span class="sxs-lookup"><span data-stu-id="7602d-146">In Internet Explorer, locate and open http://<contoso_machine>/CertSrv.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7602d-147">ステップ 1 で、Contoso または Fabrikam のコンピューター上の http://<contoso_machine>/CertSrv を開きます。</span><span class="sxs-lookup"><span data-stu-id="7602d-147">In step 1, open http://<contoso_machine>/CertSrv on the Contoso or Fabrikam computer.</span></span>  
  
2.  <span data-ttu-id="7602d-148">Microsoft 証明書サービス ウィザードへようこそ ページで、**証明書を要求**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-148">On the Microsoft Certificate Services Wizard Welcome page, click **Request a certificate**.</span></span>  
  
3.  <span data-ttu-id="7602d-149">要求の証明書 ページで、をクリックして**証明書の要求の高度な**します。</span><span class="sxs-lookup"><span data-stu-id="7602d-149">On the Request a Certificate page, click **Advanced Certificate Request**.</span></span>  
  
4.  <span data-ttu-id="7602d-150">[証明書の要求の選択] ページで、**証明書の要求を送信**でファイルを使用して、base 64 エンコード CMC または PKCS #10 または base 64 エンコード PKCS #7 ファイルを使用して、更新要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="7602d-150">On the Advanced Certificate Request page, click **Submit a certificate request** by using a base-64-encoded CMC or PKCS #10 file, or submit a renewal request by using a base-64-encoded PKCS #7 file.</span></span>  
  
5.  <span data-ttu-id="7602d-151">メモ帳などのテキスト エディターでファイル C:\certreq.txt を開き、ファイルの内容をコピーし、貼り付け、**保存された要求**証明書の要求または更新要求のページでは、ボックスの送信にし、 **送信**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-151">Open the file C:\certreq.txt in Notepad or another text editor, copy the contents of the file and paste that information in the **Saved Request** box on the Submit a Certificate Request or Renewal Request page, and then click **Submit**.</span></span>  
  
6.  <span data-ttu-id="7602d-152">証明書が発行されました ページで、をクリックして**証明書のダウンロード**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-152">On the Certificate Issued page, click **Download Certificate**.</span></span>  
  
7.  <span data-ttu-id="7602d-153">[ファイルのダウンロード] ダイアログ ボックスで、**保存**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-153">In the File Download dialog box, click **Save**.</span></span>  
  
8.  <span data-ttu-id="7602d-154">名前を付けて保存 ダイアログ ボックスで、保存する証明書\<ドライブ\>: \Certs\SSLCert.cer をクリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-154">In the Save As dialog box, save the certificate to \<drive\>:\Certs\SSLCert.cer, and then click **Save**.</span></span>  
  
### <a name="to-import-the-server-certificate-into-iis"></a><span data-ttu-id="7602d-155">サーバー証明書を IIS にインポートするには</span><span class="sxs-lookup"><span data-stu-id="7602d-155">To import the server certificate into IIS</span></span>  
  
1.  <span data-ttu-id="7602d-156">をクリックして**開始**、 をポイント**管理ツール**、順にクリック**インターネット インフォメーション サービス (IIS) マネージャー**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-156">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="7602d-157">インターネット インフォメーション サービスの左ペインでをクリックして **(ローカル コンピューター)**、ダブルクリックして**サーバー証明書**右側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="7602d-157">In the Internet Information Services left pane, click **(local computer)**, double click **Server Certificates** in the right pane.</span></span> <span data-ttu-id="7602d-158">選択**証明書要求の完全な**[操作] ウィンドウからです。</span><span class="sxs-lookup"><span data-stu-id="7602d-158">Select **Complete Certificate Request** from the Actions pane.</span></span>  
  
3.  <span data-ttu-id="7602d-159">証明機関の応答の指定 ダイアログ ボックスに「 **\<ドライブ\>: \Certs\SSLCert.cer**で**証明機関の応答を含むファイルの名前**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="7602d-159">In Specify Certificate Authority Response dialog box type **\<drive\>:\Certs\SSLCert.cer** in **File name containing the certification authority’s response** text box.</span></span> <span data-ttu-id="7602d-160">フレンドリ名テキスト ボックスに「 **ContosoSSLCert**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-160">In Friendly name text box type **ContosoSSLCert**.</span></span>  
  
### <a name="to-enable-ssl-bindings-for-iis"></a><span data-ttu-id="7602d-161">IIS で SSL バインドを有効にするには</span><span class="sxs-lookup"><span data-stu-id="7602d-161">To enable SSL bindings for IIS</span></span>  
  
1.  <span data-ttu-id="7602d-162">をクリックして**開始**、 をポイント**管理ツール**、順にクリック**インターネット インフォメーション サービス (IIS) マネージャー**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-162">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="7602d-163">インターネット インフォメーション サービスの左ペインで、展開 **(ローカル コンピューター)**、展開**サイト**を右クリックして**既定の Web サイト**、クリックして**編集バインド**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-163">In the Internet Information Services left pane, expand **(local computer)**, expand **Sites**, right-click **Default Web Site**, and then click **Edit Bindings**.</span></span>  
  
3.  <span data-ttu-id="7602d-164">[サイト バインド] ダイアログ ボックス**追加**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-164">In Site Bindings dialog box click **Add**.</span></span> <span data-ttu-id="7602d-165">サイト バインドの追加 ダイアログ ボックスで選択**https**型ドロップダウンから、次のように選択します**ContosoSSLCert** SSL 証明書ドロップダウンから、 をクリック**OK**、 をクリック**閉じる**。</span><span class="sxs-lookup"><span data-stu-id="7602d-165">In the Add Site Binding dialog box select **https** from Type drop down, select **ContosoSSLCert** from SSL certificate drop down, click **OK**, click **Close**.</span></span>  
  
### <a name="to-import-the-server-certificate-into-iis"></a><span data-ttu-id="7602d-166">サーバー証明書を IIS にインポートするには</span><span class="sxs-lookup"><span data-stu-id="7602d-166">To import the server certificate into IIS</span></span>  
  
1.  <span data-ttu-id="7602d-167">をクリックして**開始**、 をポイント**管理ツール**、順にクリック**インターネット インフォメーション サービス (IIS) マネージャー**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-167">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="7602d-168">インターネット インフォメーション サービスの左ペインで、展開 **\<**  *computer_name* \> (*ローカル コンピューター*)、展開**Webサイト**を右クリックして**既定の Web サイト**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-168">In the Internet Information Services left pane, expand **\<***computer_name*\> (*local computer*), expand **Web Sites**, right-click **Default Web Site**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="7602d-169">既定の Web サイトのプロパティ ダイアログ ボックスで、**ディレクトリ セキュリティ** タブで、をクリックして**サーバー証明書**を開始する、 **IIS 証明書ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-169">In the Default Web Site Properties dialog box, on the **Directory Security** tab, click **Server Certificate** to start the **IIS Certificate Wizard**.</span></span>  
  
4.  <span data-ttu-id="7602d-170">**Web サーバー証明書ウィザードへようこそ** ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-170">On the **Welcome to the Web Server Certificate Wizard** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="7602d-171">**保留中の証明書の要求**] ページで、[**保留中の要求を処理し、証明書をインストール**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-171">On the **Pending Certificate Request** page, select **Process the pending request and install the certificate**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="7602d-172">**保留中の要求を処理**] ページの [、**パスとファイル名**ボックスに、入力**\<ドライブ\>: \Certs\SSLCert.cer** (またはそのファイルを参照)クリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-172">On the **Process a Pending Request** page, in the **Path and file name** box, type **\<drive\>:\Certs\SSLCert.cer** (or browse to that file) and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="7602d-173">**SSL ポート ページ**をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-173">On the **SSL Port page**, click **Next**.</span></span>  
  
8.  <span data-ttu-id="7602d-174">**証明書の概要**] ページで [**次**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-174">On the **Certificate Summary** page, click **Next**.</span></span>  
  
9. <span data-ttu-id="7602d-175">**Web サーバー証明書ウィザードの完了**] ページで [**完了**です。</span><span class="sxs-lookup"><span data-stu-id="7602d-175">On the **Completing the Web Server Certificate Wizard** page, click **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7602d-176">参照</span><span class="sxs-lookup"><span data-stu-id="7602d-176">See Also</span></span>  
 [<span data-ttu-id="7602d-177">Contoso ソリューションの作成と構成</span><span class="sxs-lookup"><span data-stu-id="7602d-177">Creating and Configuring the Contoso Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-the-contoso-solution.md)