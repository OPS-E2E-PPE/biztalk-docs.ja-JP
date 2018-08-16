---
title: BizTalk Adapters for Enterprise Applications インストール |Microsoft Docs
description: 要件と BizTalk Server では、JD Edwards OneWorld では、JD Edwards EnterpriseOne では、PeopleSoft Enterprise、TIBCO Rendezvous では、TIBCO Enterprise Message Service のインストール手順
ms.custom: ''
ms.date: 10/13/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7777b7027e51460e79a6dff6a591d8faa4fe57e3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987523"
---
# <a name="install-and-configure-the-microsoft-biztalk-adapters-for-enterprise-applications"></a><span data-ttu-id="dfe01-103">インストールし、Microsoft BizTalk Adapters for Enterprise Applications に構成します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-103">Install and configure the Microsoft BizTalk Adapters for Enterprise Applications</span></span> 
  
 <span data-ttu-id="dfe01-104">Microsoft BizTalk Adapters for Enterprise Applications には、次のアダプターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="dfe01-104">Microsoft BizTalk Adapters for Enterprise Applications includes the following adapters:</span></span>  
  
-   <span data-ttu-id="dfe01-105">Microsoft BizTalk Adapter for JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="dfe01-105">Microsoft BizTalk Adapter for JD Edwards OneWorld</span></span>  
  
-   <span data-ttu-id="dfe01-106">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne</span><span class="sxs-lookup"><span data-stu-id="dfe01-106">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne</span></span>  
  
-   <span data-ttu-id="dfe01-107">Microsoft BizTalk Adapter for PeopleSoft Enterprise</span><span class="sxs-lookup"><span data-stu-id="dfe01-107">Microsoft BizTalk Adapter for PeopleSoft Enterprise</span></span>  
  
-   <span data-ttu-id="dfe01-108">Microsoft BizTalk Adapter for TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="dfe01-108">Microsoft BizTalk Adapter for TIBCO Rendezvous</span></span>  
  
-   <span data-ttu-id="dfe01-109">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service</span><span class="sxs-lookup"><span data-stu-id="dfe01-109">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service</span></span>  


> [!IMPORTANT]
> - <span data-ttu-id="dfe01-110">構成変更を加える前に、すべてのデータをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-110">Back up all data before you make any configuration changes</span></span>
> - <span data-ttu-id="dfe01-111">構成変更を加える前に、特定のエンタープライズ アプリケーションを経験するある必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-111">You must be experienced with the specific enterprise application before you make any configuration changes</span></span>
  
## <a name="supported-versions--requirements"></a><span data-ttu-id="dfe01-112">サポートされているバージョンと要件</span><span class="sxs-lookup"><span data-stu-id="dfe01-112">Supported versions & requirements</span></span>

||<span data-ttu-id="dfe01-113">要件</span><span class="sxs-lookup"><span data-stu-id="dfe01-113">Requirements</span></span>|  
|---|---|
|<span data-ttu-id="dfe01-114">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="dfe01-114">Operating System</span></span>|<span data-ttu-id="dfe01-115">アダプターには、BizTalk Server と同じ OS がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="dfe01-115">The adapter supports the same OS as BizTalk Server:</span></span><ul><li>[<span data-ttu-id="dfe01-116">BizTalk Server 2016 の要件</span><span class="sxs-lookup"><span data-stu-id="dfe01-116">BizTalk Server 2016 requirements</span></span>](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)</li><li>[<span data-ttu-id="dfe01-117">BizTalk Server 2013 R2/2013 の要件</span><span class="sxs-lookup"><span data-stu-id="dfe01-117">BizTalk Server 2013 R2 / 2013 requirements</span></span>](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md)</li></ul>|
|<span data-ttu-id="dfe01-118">サポートされている enterprise システム</span><span class="sxs-lookup"><span data-stu-id="dfe01-118">Supported enterprise system</span></span>|<span data-ttu-id="dfe01-119">[サポートされている基幹業務 (LOB) とエンタープライズ システム](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)サポートされているバージョンを一覧表示</span><span class="sxs-lookup"><span data-stu-id="dfe01-119">[Supported Line-of-Business (LOB) and Enterprise systems](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx) lists the supported versions</span></span> |
|<span data-ttu-id="dfe01-120">JD Edwards OneWorld XE</span><span class="sxs-lookup"><span data-stu-id="dfe01-120">JD Edwards OneWorld XE</span></span> | <ul><li><span data-ttu-id="dfe01-121">Windows 上の JD Edwards エンタープライズ サーバー</span><span class="sxs-lookup"><span data-stu-id="dfe01-121">JD Edwards Enterprise server on Windows</span></span></li><li><span data-ttu-id="dfe01-122">Windows 上の JD Edwards Deployment サーバー</span><span class="sxs-lookup"><span data-stu-id="dfe01-122">JD Edwards Deployment server on Windows</span></span></li></ul>|
|<span data-ttu-id="dfe01-123">JD Edwards EnterpriseOne</span><span class="sxs-lookup"><span data-stu-id="dfe01-123">JD Edwards EnterpriseOne</span></span> | <span data-ttu-id="dfe01-124">アダプターは、データベースのドライバーが必要になる JDBC を使用して、JD Edwards EnterpriseOne API を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-124">The adapter calls the JD Edwards EnterpriseOne API that uses JDBC, which needs a driver for the database.</span></span> <span data-ttu-id="dfe01-125">JD Edwards EnterpriseOne を SQL データベースとともにインストールする場合、MS-SQL のドライバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="dfe01-125">If you install JD Edwards EnterpriseOne with a SQL database, you need MS-SQL drivers.</span></span> <span data-ttu-id="dfe01-126">同様に、Oracle データベースを JD Edwards EnterpriseOne をインストールした場合に、Oracle ドライバーを必要または、DB2 ドライバーが必要な DB2 データベースをインストールした場合。</span><span class="sxs-lookup"><span data-stu-id="dfe01-126">Similarly if you installed JD Edwards EnterpriseOne with an Oracle database, you need Oracle drivers; or if you installed with a DB2 database, you need DB2 drivers.</span></span> |
|<span data-ttu-id="dfe01-127">PeopleSoft Enterprise</span><span class="sxs-lookup"><span data-stu-id="dfe01-127">PeopleSoft Enterprise</span></span> | <ul><li><span data-ttu-id="dfe01-128">Sun Systems Java Development Kit (JDK)</span><span class="sxs-lookup"><span data-stu-id="dfe01-128">Sun Systems Java Development Kit (JDK)</span></span></li><li><span data-ttu-id="dfe01-129">PeopleSoft ツール リリース</span><span class="sxs-lookup"><span data-stu-id="dfe01-129">PeopleSoft Tools release</span></span></li><li><span data-ttu-id="dfe01-130">PeopleSoft アプリケーションをリリースします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-130">PeopleSoft Applications release</span></span></li><li><span data-ttu-id="dfe01-131">このアダプターには、PeopleSoft アプリケーションへの変更が必要です。</span><span class="sxs-lookup"><span data-stu-id="dfe01-131">This adapter requires a modification to the PeopleSoft application.</span></span> <span data-ttu-id="dfe01-132">コンポーネント インターフェイスを使用するには、PeopleSoft にカスタム コンポーネント インターフェイスの GET_CI_INFO をアップロードします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-132">To use component interfaces, upload a custom component interface, GET_CI_INFO, into PeopleSoft.</span></span> <span data-ttu-id="dfe01-133">GET_CI_INFO.pc は Program files \common files \microsoft BizTalk adapters Enterprise Applications\PeopleSoft Enterprise(r) \Config\ です。</span><span class="sxs-lookup"><span data-stu-id="dfe01-133">GET_CI_INFO.pc is in Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise(r)\Config\.</span></span></li></ul>|
|<span data-ttu-id="dfe01-134">TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="dfe01-134">TIBCO Rendezvous</span></span> | <ul><li><span data-ttu-id="dfe01-135">TIBCO Rendezvous の実行時コンポーネントは、BizTalk Adapter for TIBCO Rendezvous が実行されているコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-135">The TIBCO Rendezvous run-time component must be installed on the computer where BizTalk Adapter for TIBCO Rendezvous is running</span></span></li><li><span data-ttu-id="dfe01-136">TIBCO Rendezvous のライセンスは、BizTalk Adapter for TIBCO Rendezvous が実行されているコンピューターで構成される必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-136">The TIBCO Rendezvous license must be configured on the computer where BizTalk Adapter for TIBCO Rendezvous is running.</span></span></li><li><span data-ttu-id="dfe01-137">TIBCO Rendezvous のバイナリ ディレクトリが、環境変数の PATH の値、または BizTalk Server の各 Rendezvous ポートで指定されて、アダプターに認識されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-137">The TIBCO Rendezvous binaries directory must be visible to the adapter: either in the Environment variables PATH value, or specified on each Rendezvous port in BizTalk Server.</span></span> <span data-ttu-id="dfe01-138">これは、Rendezvous のアセンブリが、そのライブラリと実行可能ファイルを見つけるために必要です。</span><span class="sxs-lookup"><span data-stu-id="dfe01-138">This is necessary for the Rendezvous assembly to find its libraries and executable.</span></span></li></ul>|
|<span data-ttu-id="dfe01-139">TIBCO Enterprise Message Service</span><span class="sxs-lookup"><span data-stu-id="dfe01-139">TIBCO Enterprise Message Service</span></span> | <span data-ttu-id="dfe01-140">Enterprise Message Service (EMS) のバージョン 5.x 以降、クライアント SDK (TIBCO EMS c# API を使用) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="dfe01-140">Enterprise Message Service (EMS) version 5.x and above includes a client SDK (using the TIBCO EMS C# API).</span></span> <span data-ttu-id="dfe01-141">BizTalk Adapter for TIBCO EMS では、これを使用して、サーバーと通信します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-141">BizTalk Adapter for TIBCO EMS uses this to communicate with the server.</span></span> |


## <a name="jd-edwards-oneworld-xe"></a><span data-ttu-id="dfe01-142">JD Edwards OneWorld XE</span><span class="sxs-lookup"><span data-stu-id="dfe01-142">JD Edwards OneWorld XE</span></span>

<span data-ttu-id="dfe01-143">このセクションでには、BizTalk Server と JD Edwards OneWorld XE の Microsoft BizTalk Adapter の使用に関する重要な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="dfe01-143">This sections includes key information on using the Microsoft BizTalk Adapter for JD Edwards OneWorld XE with BizTalk Server.</span></span>
  
### <a name="create-the-jar-files"></a><span data-ttu-id="dfe01-144">JAR ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-144">Create the JAR Files</span></span>
 <span data-ttu-id="dfe01-145">ここでは、Microsoft BizTalk Adapter for JD Edwards OneWorld を操作するための JD Edwards OneWorld の要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-145">This section describes the requirements for JD Edwards OneWorld to work with Microsoft BizTalk Adapter for JD Edwards OneWorld.</span></span>  
  
#### <a name="jar-files-and-the-classpath"></a><span data-ttu-id="dfe01-146">JAR ファイルと CLASSPATH</span><span class="sxs-lookup"><span data-stu-id="dfe01-146">JAR Files and the CLASSPATH</span></span>  
 <span data-ttu-id="dfe01-147">JD Edwards OneWorld JAR ファイルは、アダプターに使用可能なである必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-147">JD Edwards OneWorld JAR files must be available to the adapter.</span></span> <span data-ttu-id="dfe01-148">たとえば、バージョンの B7.3.3.3 に接続する場合、次の jar ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="dfe01-148">For instance, to connect to B7.3.3.3 Version, the following jar files are required.</span></span> <span data-ttu-id="dfe01-149">接続するサーバーに応じて、jar ファイルの一覧を変更する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-149">Depending on the server you connect, the jar file list may change:</span></span>
  
- <span data-ttu-id="dfe01-150">Connector.jar</span><span class="sxs-lookup"><span data-stu-id="dfe01-150">Connector.jar</span></span>    
- <span data-ttu-id="dfe01-151">Kernel.jar</span><span class="sxs-lookup"><span data-stu-id="dfe01-151">Kernel.jar</span></span>  
  
  <span data-ttu-id="dfe01-152">これらのファイルは、JD Edwards OneWorld を実行しているコンピューターの次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-152">These files are located on a computer running JD Edwards OneWorld, at the following locations:</span></span>  
  
- <span data-ttu-id="dfe01-153">JD Edwards OneWorld XE_install_Directory\System\classes\Connector.jar</span><span class="sxs-lookup"><span data-stu-id="dfe01-153">JD Edwards OneWorld XE_install_Directory\System\classes\Connector.jar</span></span>    
- <span data-ttu-id="dfe01-154">JD Edwards OneWorld XE_install_Directory\System\classes\Kernel.jar</span><span class="sxs-lookup"><span data-stu-id="dfe01-154">JD Edwards OneWorld XE_install_Directory\System\classes\Kernel.jar</span></span>  
  
  <span data-ttu-id="dfe01-155">これらのファイルは任意の場所にコピーできますが、JAR ファイルの場所は CLASSPATH に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-155">You can copy these files to any location; however, you must specify the location of the JAR files in the CLASSPATH.</span></span> <span data-ttu-id="dfe01-156">CLASSPATH には、ファイルの完全なパスと JAR ファイルの名前の両方 (セミコロンで区切る) を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-156">The CLASSPATH must include both the full path of the file and the name of the JAR file (separated by a semicolon).</span></span>  
  
  <span data-ttu-id="dfe01-157">BizTalk Adapter for JD Edwards OneWorld では、JD Edwards OneWorld で使用するための JDEJAccess JAR ファイルを提供します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-157">BizTalk Adapter for JD Edwards OneWorld provides the JDEJAccess JAR file for use with JD Edwards OneWorld.</span></span> <span data-ttu-id="dfe01-158">既定では、JDEJAccess.jar ファイルが参照されている*Program files \common files \microsoft BizTalk Adapters for Enterprise applications \j.d. します。Edwards OneWorld(r) \classes\JDEJAccess.jar*します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-158">By default, the JDEJAccess.jar file is referenced from *Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\J.D. Edwards OneWorld(r)\classes\JDEJAccess.jar*.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="dfe01-159">BizTalk Adapter for JD Edwards OneWorld を使用するには、jdeinterop.ini ファイルの登録を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-159">You must verify the registration of the jdeinterop.ini file before you can use BizTalk Adapter for JD Edwards OneWorld.</span></span> <span data-ttu-id="dfe01-160">このファイルへのパスを含めることを確認、 **JDE トランスポートのプロパティ**で BizTalk Server 送信ポートを作成するときのページします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-160">Make sure that you include a path to this file in the **JDE Transport Property** page when you create the send port in BizTalk Server.</span></span> <span data-ttu-id="dfe01-161">詳細については、「カスタマイズ jdeinterop.ini ファイル」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfe01-161">For a complete explanation, see "Customize the jdeinterop.ini File."</span></span>  
  
#### <a name="create-the-btslibinteropjar-file"></a><span data-ttu-id="dfe01-162">BTSLIBinterop.jar ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-162">Create the BTSLIBinterop.jar File</span></span>  
<span data-ttu-id="dfe01-163">ファイルを作成し、アダプターによってアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-163">Create the file, and confirm it can be accessed by the adapter.</span></span> <span data-ttu-id="dfe01-164">次の例をガイドとして使用します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-164">Use the following sample as a guide:</span></span>  
  
1.  <span data-ttu-id="dfe01-165">次のコードが含まれた BTSLIB.cmd ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-165">Create the BTSLIB.cmd file that contains the following code:</span></span>  
  
    ```  
    define library BTSLIB  
    login  
    library BTSLIB  
    interface JDEAdapter  
    import B5500900  
    build  
    logout  
    ```  
  
2.  <span data-ttu-id="dfe01-166">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-166">Run the following command:</span></span>  
  
    ```  
    GenJava  /cmd  .\BTSLIB.cmd  
    ```  
  
### <a name="verify-your-setup"></a><span data-ttu-id="dfe01-167">設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-167">Verify your setup</span></span>  
  
1.  <span data-ttu-id="dfe01-168">サービス パック番号を含む、サポートされているバージョンを使用して ([サポートされている基幹業務 (LOB) とエンタープライズ システム](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx))。</span><span class="sxs-lookup"><span data-stu-id="dfe01-168">Use a supported version, including service pack number ([Supported Line-of-Business (LOB) and Enterprise systems](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)).</span></span> <span data-ttu-id="dfe01-169">サービス パック (ESU および ASU) では、システム バイナリを更新します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-169">Service packs (ESUs and ASUs) update the system binaries.</span></span> <span data-ttu-id="dfe01-170">前提条件のサービス パックには、インポート用の ASU/ESU というメニューの選択項目が用意されています。</span><span class="sxs-lookup"><span data-stu-id="dfe01-170">The prerequisite service pack provides the ASU/ESU menu choice for import.</span></span>  
  
2.  <span data-ttu-id="dfe01-171">C ドライブとは異なる場合、ログ記録の適切なドライブを使用する jdeinterop.ini ファイルを構成します。たとえば、ディレクトリの TEMP ディレクトリが領域外の場合に、JD Edwards OneWorld の更新が失敗します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-171">Configure the jdeinterop.ini file to use the correct drive for logging, if it differs from drive C. For example, your JD Edwards OneWorld update can fail if the TEMP directory is out of space.</span></span>  
  
3.  <span data-ttu-id="dfe01-172">JD Edwards OneWorld のフィールドの左右の埋め込み用の構成ファイルを追加する必要があるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-172">Determine whether you must add a configuration file for the left/right padding of the JD Edwards OneWorld fields.</span></span>  
  
4.  <span data-ttu-id="dfe01-173">コンピューター上の任意のプログラムから javac コマンドと java コマンドを有効にするには、JAVA_HOME 環境変数が Java Development Kit (JDK) のインストール場所を指していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-173">Verify that your JAVA_HOME environment variable is pointing to your Java Development Kit (JDK) installation to enable the javac and java commands from any program on the computer.</span></span>  
  
5.  <span data-ttu-id="dfe01-174">CLASSPATH 環境変数が設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-174">Verify that the CLASSPATH environment variable is set.</span></span> <span data-ttu-id="dfe01-175">これにより、BizTalk Adapter for JD Edwards OneWorld を Kernel.jar と Connect.jar ファイルを検索できます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-175">This enables BizTalk Adapter for JD Edwards OneWorld to locate the Kernel.jar and Connect.jar files.</span></span>  
  
    <span data-ttu-id="dfe01-176">JAR ファイルのパスは、大文字小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-176">The path of the JAR files is case sensitive.</span></span>  
  
6.  <span data-ttu-id="dfe01-177">次のコマンド (大文字小文字が区別されます) を入力して、環境をテストします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-177">Test the environment by typing the following command, which is case sensitive.</span></span>  
  
    ```  
    javap -s -p com.microsoft.jde.JDEJAccess  
    ```  
  
7.  <span data-ttu-id="dfe01-178">指定するコマンドの javap は、Java クラス ファイルの逆アセンブラーです。</span><span class="sxs-lookup"><span data-stu-id="dfe01-178">The command you give, javap, is the Java Class File Disassembler:</span></span>  
  
    ```  
    http://java.sun.com/j2se/1.3/docs/tooldocs/solaris/javap.html  
    ```  
  
8.  <span data-ttu-id="dfe01-179">`javap`コマンド クラス ファイルを逆アセンブルします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-179">The `javap` command disassembles a class file.</span></span> <span data-ttu-id="dfe01-180">その出力は、使用するオプションによって異なります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-180">Its output depends on the options used.</span></span> <span data-ttu-id="dfe01-181">オプションが使用されていない場合、javap は、保護されているパッケージとパブリック フィールドとそれに渡されるクラスのメソッドを出力します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-181">If no options are used, javap prints out the package, protected, and public fields and methods of the classes passed to it.</span></span> <span data-ttu-id="dfe01-182">javap では、その出力を stdout に出力します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-182">javap prints its output to stdout.</span></span>  
  
     <span data-ttu-id="dfe01-183">エラーがなければ、すべての Java ファイルとそれらの依存関係は CLASSPATH にあります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-183">If there are no errors, all the Java files and their dependencies are in the CLASSPATH.</span></span>  
  
9. <span data-ttu-id="dfe01-184">ローカル ホスト ファイルを構成することで、DNS 解決を設定 (*C:\WINNT\system32\drivers\etc\hosts*)、JD Edwards OneWorld システムのサーバーの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-184">Set up the DNS resolution by configuring the local host file (*C:\WINNT\system32\drivers\etc\hosts*), with the server name of the JD Edwards OneWorld system.</span></span>  
  
### <a name="create-and-install-the-custom-package"></a><span data-ttu-id="dfe01-185">作成し、カスタム パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-185">Create and install the custom package</span></span>  
<span data-ttu-id="dfe01-186">BizTalk Adapter for JD Edwards OneWorld の使用に BTSREL カスタム パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-186">Install the BTSREL custom package to use BizTalk Adapter for JD Edwards OneWorld.</span></span> <span data-ttu-id="dfe01-187">このセクションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-187">This section describes:</span></span>  
  
-   <span data-ttu-id="dfe01-188">JD Edwards OneWorld のカスタム パッケージの作成プロセス</span><span class="sxs-lookup"><span data-stu-id="dfe01-188">The JD Edwards OneWorld custom package-creation process</span></span>  
-   <span data-ttu-id="dfe01-189">作成して、BTSREL をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="dfe01-189">How to create and install BTSREL</span></span>  
-   <span data-ttu-id="dfe01-190">JD Edwards OneWorld で作成された BTSREL オブジェクト</span><span class="sxs-lookup"><span data-stu-id="dfe01-190">The BTSREL objects created in JD Edwards OneWorld</span></span>
  
> [!NOTE]
>  <span data-ttu-id="dfe01-191">BTSREL.exe はカスタム パッケージです (JD Edwards OneWorld の用語では、自動化されたソフトウェア更新プログラム (ASU))。</span><span class="sxs-lookup"><span data-stu-id="dfe01-191">BTSREL.exe is a custom package (an automated software update, or ASU, in JD Edwards OneWorld terminology).</span></span> <span data-ttu-id="dfe01-192">このパッケージには、メタデータを抽出するためのビジネス関数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="dfe01-192">It contains business functions to extract metadata.</span></span> <span data-ttu-id="dfe01-193">カスタム パッケージは、JD Edwards OneWorld の特定の構成とバージョン用に作成してください。</span><span class="sxs-lookup"><span data-stu-id="dfe01-193">A custom package should be created for a specific configuration and version of JD Edwards OneWorld.</span></span>  
  
#### <a name="define-a-custom-package"></a><span data-ttu-id="dfe01-194">カスタム パッケージを定義します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-194">Define a custom package</span></span>  
 <span data-ttu-id="dfe01-195">カスタム パッケージとは、リリース後の成果物であり、法規制の変更や機能強化などの特定の目的のためのソフトウェア変更を提供します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-195">A custom package is a post-release deliverable that provides software changes for specific purposes, such as regulatory changes or enhancements.</span></span> <span data-ttu-id="dfe01-196">これらのカスタム パッケージは、特定の機能向けに作成されます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-196">These custom packages are created for specific functionality.</span></span> <span data-ttu-id="dfe01-197">たとえば、BTSREL はメタデータを抽出するために作成されます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-197">For example, BTSREL is created to extract metadata.</span></span> <span data-ttu-id="dfe01-198">BTSREL カスタム パッケージをインストールすると、JD Edwards OneWorld 環境内の選択したモジュールが更新されます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-198">When the BTSREL custom package is installed, it updates selected modules in the JD Edwards OneWorld environment.</span></span> <span data-ttu-id="dfe01-199">更新を行うには、適切な JD Edwards OneWorld の環境に BTSREL オブジェクトをマージする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-199">To update, BTSREL objects must be merged into the appropriate JD Edwards OneWorld environment.</span></span> <span data-ttu-id="dfe01-200">BTSREL によって更新されるモジュールの詳細な一覧については、「モジュールの一覧」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfe01-200">For a detailed list of modules updated by BTSREL, see the list of modules.</span></span>  
  
#### <a name="install-the-btsrel-custom-package"></a><span data-ttu-id="dfe01-201">BTSREL カスタム パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-201">Install the BTSREL custom package</span></span>   
<span data-ttu-id="dfe01-202">ダウンロード[BTSREL](https://www.microsoft.com/download/details.aspx?id=56113)します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-202">Download [BTSREL](https://www.microsoft.com/download/details.aspx?id=56113).</span></span> <span data-ttu-id="dfe01-203">展開サーバーにインストールし、エンタープライズ サーバーに配置します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-203">Install it on the deployment server, and then deploy it to the enterprise server.</span></span>  
  
 <span data-ttu-id="dfe01-204">既存の BTSREL.exe パッケージは、B7333 バージョンと直接動作します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-204">The existing BTSREL.exe package directly works with the B7333 version.</span></span> <span data-ttu-id="dfe01-205">パッケージがし B7334 バージョンでは、作業をするには。</span><span class="sxs-lookup"><span data-stu-id="dfe01-205">For the package to work with the B7334 version, then:</span></span>  
  
1. <span data-ttu-id="dfe01-206">BTSREL.exe をダウンロードして、BTSREL.exe の内容を作業フォルダーに展開します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-206">Download and extract the contents of BTSREL.exe to your working folder.</span></span>  
  
2. <span data-ttu-id="dfe01-207">両方を変更、 **ReleaseLevelRequired**と**リリース**B7334 に Deployment.Inf ファイル内の値。</span><span class="sxs-lookup"><span data-stu-id="dfe01-207">Modify both the **ReleaseLevelRequired** and the **Release** values to B7334 in the Deployment.Inf file.</span></span>  
  
3. <span data-ttu-id="dfe01-208">セットアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-208">Run the Setup.</span></span>  
  
   <span data-ttu-id="dfe01-209">BTSREL をインストールするには次が必要です。</span><span class="sxs-lookup"><span data-stu-id="dfe01-209">To install BTSREL, the following are required:</span></span>  
  
-   <span data-ttu-id="dfe01-210">展開サーバーのインストール</span><span class="sxs-lookup"><span data-stu-id="dfe01-210">Deployment server installation</span></span>    
-   <span data-ttu-id="dfe01-211">Installation Workbench</span><span class="sxs-lookup"><span data-stu-id="dfe01-211">Installation Workbench</span></span>  
  
#### <a name="install-btsrel-on-the-deployment-server"></a><span data-ttu-id="dfe01-212">展開サーバー上の BTSREL をインストールします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-212">Install BTSREL on the deployment server</span></span>  
 <span data-ttu-id="dfe01-213">カスタムでは、Windows オペレーティング システムでは、上でのみ機能をパッケージ化し、展開サーバーで使用されます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-213">The custom package only works on a Windows operating system, and is used with the deployment server.</span></span> <span data-ttu-id="dfe01-214">展開サーバー上に構築され、エンタープライズ サーバーに配置しする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-214">It must be built on the deployment server, and then deployed to the enterprise server.</span></span> <span data-ttu-id="dfe01-215">エンタープライズ サーバーは、通常実稼働サーバーで、Windows または UNIX のオペレーティング システムのいずれかの上に存在します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-215">The enterprise server is usually a production server, and can be on either a Windows or UNIX operating system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dfe01-216">ASU を JD Edwards OneWorld デプロイメント サーバーに適用する場合であることを確認**Update**モード。</span><span class="sxs-lookup"><span data-stu-id="dfe01-216">When applying the ASU to the JD Edwards OneWorld deployment server, verify that you are in **Update** mode.</span></span> <span data-ttu-id="dfe01-217">**実証**モードが一方、ASU にバグがないことを確認**Update** ASU を適用するときのモードを指定します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-217">The **Proof** mode verifies that there are no bugs in the ASU, whereas **Update** mode is designated for when you apply the ASU.</span></span>  
  
1.  <span data-ttu-id="dfe01-218">ユーザーと展開サーバーへのサインイン**JDE**します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-218">Sign in to the deployment server as user **JDE**.</span></span>  
  
2.  <span data-ttu-id="dfe01-219">デプロイメント サーバー (root) の /B7 フォルダーに BTSREL という新しいフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-219">Create a new folder, named BTSREL, on the Deployment Server (root) /B7 folder.</span></span>  
  
3.  <span data-ttu-id="dfe01-220">BTSREL.exe を新しく作成した BTSREL フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-220">Copy BTSREL.exe to the newly created BTSREL folder.</span></span>  
  
4.  <span data-ttu-id="dfe01-221">BTSREL.exe を .../B7/BTSREL フォルダーで実行します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-221">Run BTSREL.exe from the.../B7/BTSREL folder.</span></span> <span data-ttu-id="dfe01-222">インストールのマネージャーが自動的に開始されます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-222">The installation manager automatically starts.</span></span>  
  
5.  <span data-ttu-id="dfe01-223">セットアップ ウィンドウで、選択**次**、し、**完了**。</span><span class="sxs-lookup"><span data-stu-id="dfe01-223">In the setup window, select **Next**, and then select **Finish**.</span></span> <span data-ttu-id="dfe01-224">インストールが成功した場合、メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-224">A message displays if the installation is successful.</span></span>  
  
6.  <span data-ttu-id="dfe01-225">として JDEPLAN 環境にサインイン、**JDE** JD Edwards OneWorld デプロイメント サーバー上のユーザー。</span><span class="sxs-lookup"><span data-stu-id="dfe01-225">Sign to the JDEPLAN environment as the**JDE** user on the JD Edwards OneWorld deployment server.</span></span>  
  
    1.  <span data-ttu-id="dfe01-226">SAR #4533357 が含まれる電子的ソフトウェア更新プログラム (ESU) がシステムにインストールされていない場合は、選択**ソフトウェア更新プログラムの**から、**システム インストール ツール**メニュー (GH9612)。</span><span class="sxs-lookup"><span data-stu-id="dfe01-226">If the electronic software update (ESU) that includes SAR #4533357 is not installed on the system, select **Software Updates** from the **System Installation Tools** menu (GH9612).</span></span>  
  
    2.  <span data-ttu-id="dfe01-227">オプション 1 に 02 と入力します、**処理オプション**パネル。</span><span class="sxs-lookup"><span data-stu-id="dfe01-227">Enter 02 for option 1 in the **Processing Options** panel.</span></span>  
  
    3.  <span data-ttu-id="dfe01-228">SAR #4533357 が含まれる ESU がシステムにインストールされている場合は、選択**アプリケーション ソフトウェアの更新**から、**システム インストール ツール**メニュー (GH9612)。</span><span class="sxs-lookup"><span data-stu-id="dfe01-228">If the ESU that includes SAR #4533357 has been installed on the system, select **Application Software Update** from the **System Installation Tools** menu (GH9612).</span></span>  
  
#### <a name="install-btsrel-on-the-jd-edwards-oneworld-workbench"></a><span data-ttu-id="dfe01-229">JD Edwards OneWorld WorkBench に BTSREL をインストールします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-229">Install BTSREL on the JD Edwards OneWorld WorkBench</span></span>  
   
1.  <span data-ttu-id="dfe01-230">**アプリケーションの更新操作**画面、BTSREL 更新プログラムをダブルクリックし、選択**次**します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-230">On the **Work with Application Update** screen, double-click the BTSREL update, and then select **Next**.</span></span>  
  
2.  <span data-ttu-id="dfe01-231">更新プログラムをインストールするを必要とする環境をダブルクリックし、選択**次**します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-231">Double-click the environments where you want the update installed, and then select **Next**.</span></span>  
  
    1.  <span data-ttu-id="dfe01-232">確認**無人 Workbench**ソフトウェアの更新を自動モードで実行する場合。</span><span class="sxs-lookup"><span data-stu-id="dfe01-232">Check **Unattended Workbench** if you want the software update to run in unattended mode.</span></span>  
  
    2.  <span data-ttu-id="dfe01-233">選択**バックアップ**(その元の仕様を復元することができます) の仕様のバックアップを修正する場合。</span><span class="sxs-lookup"><span data-stu-id="dfe01-233">Select **Backup** if you want the backup of the specifications (so that the original specifications can be restored).</span></span>  
  
3.  <span data-ttu-id="dfe01-234">**インストール プラン操作**画面をインストールする更新プログラムの計画を選択し、**選択**。</span><span class="sxs-lookup"><span data-stu-id="dfe01-234">On the **Work with Installation Plan** screen, select the plan for the update you are installing, and then **Select**.</span></span>  
  
4.  <span data-ttu-id="dfe01-235">インストールが完了したら、自動生成されるエラーに関する PDF を確認してください。</span><span class="sxs-lookup"><span data-stu-id="dfe01-235">See the automatically generated PDFs for errors after the installation is finished.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dfe01-236">エラーが発生した場合、トラブルシューティングのヒントについては『JD Edwards OneWorld Software Update Guide』を確認するか、または JD Edwards OneWorld に直接お問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="dfe01-236">If errors occur, look in the JD Edwards OneWorld Software Update Guide for troubleshooting tips, or contact JD Edwards OneWorld directly.</span></span>  
  
5.  <span data-ttu-id="dfe01-237">「に手動で登録、ビジネス関数ライブラリ」このセクションに含まれている手順を使用して、ビジネス関数ライブラリを手動で登録します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-237">Manually register the business function library using the steps included in "Manually register the business function library" in this section.</span></span>  
  
#### <a name="uninstall-the-custom-package"></a><span data-ttu-id="dfe01-238">カスタム パッケージをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-238">Uninstall the custom package</span></span>  
 <span data-ttu-id="dfe01-239">カスタム パッケージのアンインストールには要件はありません。</span><span class="sxs-lookup"><span data-stu-id="dfe01-239">There is no requirement to uninstall the custom package.</span></span> <span data-ttu-id="dfe01-240">ただし、システムをクリーンアップする場合は、異なる方法でアンインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-240">However, if you want to clean the system, you can uninstall in different ways.</span></span> <span data-ttu-id="dfe01-241">をアンインストールした後、次のメソッドのいずれかを使用してパッケージを再構築します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-241">After you uninstall, rebuild the package using one of the following methods:</span></span>  
  
- <span data-ttu-id="dfe01-242">JD Edwards OneWorld Deployment サーバー、Gh8612 を使用して、— P96470 の**行**メニューの **更新**、し、**アンインストール**します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-242">Use the JD Edwards OneWorld Deployment Server, Gh8612—P96470, on the **ROW** menu, select **Update**, and then select **Uninstall**.</span></span>    
- <span data-ttu-id="dfe01-243">すべてのカスタム オブジェクト (BTSREL) をクライアント コンピューターにチェック アウトしてから、それらを削除します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-243">Check out all the custom objects (BTSREL) to a client computer and delete them.</span></span>    
- <span data-ttu-id="dfe01-244">データベースの前のスナップショットを適用します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-244">Apply a previous snapshot of database.</span></span>  
  
  <span data-ttu-id="dfe01-245">クリーンアップ中に、JD Edwards OneWorld の他のオブジェクトに対する他のすべての変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-245">During the clean-up, verify any other modifications to the other objects of JD Edwards OneWorld.</span></span>  
  
#### <a name="manually-register-the-business-function-library"></a><span data-ttu-id="dfe01-246">ビジネス関数ライブラリを手動で登録します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-246">Manually register the business function library</span></span>  
 <span data-ttu-id="dfe01-247">JD Edwards OneWorld 製品のパッケージ化プロセスの制限のために、BizTalk Adapter for JD Edwards OneWorld 用のカスタムのビジネス関数ライブラリ DLL を JD Edwards OneWorld に手動で登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-247">Because of a limitation of the JD Edwards OneWorld product packaging process, the custom Business Function Library DLL for BizTalk Adapter for JD Edwards OneWorld must be manually registered with JD Edwards OneWorld.</span></span> <span data-ttu-id="dfe01-248">このプロセスは、次の手順で構成されます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-248">This process consists of the following steps.</span></span>
  
##### <a name="step-1-create-the-custom-business-function-library"></a><span data-ttu-id="dfe01-249">手順 1: カスタム ビジネス関数ライブラリを作成します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-249">Step 1: Create the custom business function library</span></span>  
 <span data-ttu-id="dfe01-250">JD Edwards OneWorld Object Management Workbench (OMW) を使用して、カスタムのビジネス関数ライブラリを作成します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-250">Using JD Edwards OneWorld Object Management Workbench (OMW), create the Custom Business Function Library.</span></span> <span data-ttu-id="dfe01-251">次の手順で初期セットアップを実行して、すべてのプラットフォームに適用されます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-251">The following procedure must be performed on initial setup, and applies to all platforms.</span></span>  
  
1.  <span data-ttu-id="dfe01-252">Object Management Workbench を起動 (高速なパス:「OMW」。 またはメニュー選択: GH902 オブジェクト: P98220)。</span><span class="sxs-lookup"><span data-stu-id="dfe01-252">Start the Object Management Workbench (fast path: "OMW" or menu selection: GH902 Object: P98220).</span></span>  
  
2.  <span data-ttu-id="dfe01-253">選択**追加**のオプションを選択および**ビジネス関数ライブラリ**します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-253">Select **Add**, and select the option for **Business Function Library**.</span></span>  
  
3.  <span data-ttu-id="dfe01-254">新しいビジネス関数ライブラリ オブジェクトに関する次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-254">Enter the following information for the New Business Function Library Object:</span></span>  
  
    -   <span data-ttu-id="dfe01-255">**名前:** ACBLIB</span><span class="sxs-lookup"><span data-stu-id="dfe01-255">**Name:** ACBLIB</span></span>    
    -   <span data-ttu-id="dfe01-256">**説明:** Microsoft DLL</span><span class="sxs-lookup"><span data-stu-id="dfe01-256">**Description:** Microsoft DLL</span></span>    
    -   <span data-ttu-id="dfe01-257">**製品コード:** 55</span><span class="sxs-lookup"><span data-stu-id="dfe01-257">**Product Code:** 55</span></span>    
    -   <span data-ttu-id="dfe01-258">**製品システム コード:** 55</span><span class="sxs-lookup"><span data-stu-id="dfe01-258">**Product System Code:** 55</span></span>  
  
4.  <span data-ttu-id="dfe01-259">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-259">Select **OK**.</span></span>  
  
##### <a name="step-2-rebuild-libraries-from-the-deployment-server"></a><span data-ttu-id="dfe01-260">手順 2: 配置サーバーからライブラリを再構築します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-260">Step 2: Rebuild libraries from the deployment server</span></span>  
<span data-ttu-id="dfe01-261">各プラットフォームの初期セットアップでは、次の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-261">Complete the following steps on initial setup for each platform.</span></span>  
  
1.  <span data-ttu-id="dfe01-262">BusBuild プログラムをスタンドアロン モードで起動する**開始**を選択します**実行**、し、 **busbuild.exe**します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-262">To start the BusBuild program in a standalone mode, select **Start**, select  **Run**, and then select **busbuild.exe**.</span></span>
  
2.  <span data-ttu-id="dfe01-263">JD Edwards OneWorld にパスコード (PY7333、PD7333、または DV7333) でサインインします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-263">Sign in to JD Edwards OneWorld in the pathcode (PY7333, PD7333, or DV7333).</span></span>  
  
3.  <span data-ttu-id="dfe01-264">**ライブラリの再構築**一覧で、、**ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-264">In the **Rebuild Libraries** list, select the **Build**.</span></span>  
  
##### <a name="step-3-copy-the-custom-dll"></a><span data-ttu-id="dfe01-265">手順 3: カスタム DLL をコピーします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-265">Step 3: Copy the Custom DLL</span></span>  
 <span data-ttu-id="dfe01-266">カスタムの DLL をパスコード ディレクトリから JD Edwards OneWorld の展開サーバーと JD Edwards OneWorld Enterprise サーバーは、親パッケージのディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-266">Copy the custom DLL from the pathcode directory to the parent package directories on the JD Edwards OneWorld deployment server and on the JD Edwards OneWorld Enterprise Server.</span></span>
  
<span data-ttu-id="dfe01-267">**で、JD Edwards OneWorld XE Deployment サーバー**</span><span class="sxs-lookup"><span data-stu-id="dfe01-267">**On the JD Edwards OneWorld XE Deployment Server**</span></span>  
  
1.  <span data-ttu-id="dfe01-268">ACBLIB.dll を DV7333\bin32 から DV7333\Packages\DV7333FA\bin32 にコピーします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-268">Copy ACBLIB.dll from DV7333\bin32 to DV7333\Packages\DV7333FA\bin32.</span></span>  
  
2.  <span data-ttu-id="dfe01-269">ACBLIB.def、ACBLIB.dmp、および ACBLIB.mak を DV7333\obj フォルダーから DV7333\Packages\DV7333FA\obj フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-269">Copy ACBLIB.def, ACBLIB.dmp, and ACBLIB.mak from DV7333\obj folder to DV7333\Packages\DV7333FA\obj folder.</span></span>  
  
3.  <span data-ttu-id="dfe01-270">ACBLIB.exp、ACBLIB.lib、および sACBLIB.lib を DV7333\lib32 フォルダーから DV7333\Packages\DV7333FA\lib32 フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-270">Copy ACBLIB.exp, ACBLIB.lib, and sACBLIB.lib from DV7333\lib32 folder to DV7333\Packages\DV7333FA\lib32 folder.</span></span>  
  
<span data-ttu-id="dfe01-271">**JD Edwards OneWorld Enterprise サーバー**</span><span class="sxs-lookup"><span data-stu-id="dfe01-271">**On the JD Edwards OneWorld Enterprise Server**</span></span>  
  
<span data-ttu-id="dfe01-272">各ディレクトリとファイルを作成した後、アクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-272">After each directory and file is created, verify the authorization.</span></span>  
  
1.  <span data-ttu-id="dfe01-273">ディレクトリ DV7333FA\obj ACBLIB 作成\\です。</span><span class="sxs-lookup"><span data-stu-id="dfe01-273">Create a directory ACBLIB under DV7333FA\obj\\.</span></span>  
  
2.  <span data-ttu-id="dfe01-274">ACBLIB DV7333FA\source 下のディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-274">Create a directory ACBLIB under DV7333FA\source.</span></span>  
  
3.  <span data-ttu-id="dfe01-275">b5500900.c を、デプロイメント サーバーの DV7333\source ディレクトリから DV7333FA\source\ACBLIB ディレクトリに FTP で転送します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-275">FTP b5500900.c from Deployment Server DV7333\source directory to DV7333FA\source\ACBLIB directory.</span></span>  
  
4.  <span data-ttu-id="dfe01-276">FTP の b5500900.h は展開サーバー DV7333\include ディレクトリ DV7333FA\include ディレクトリにします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-276">FTP b5500900.h from Deployment Server DV7333\include directory to DV7333FA\include directory.</span></span>  
  
##### <a name="step-4-build-a-full-package"></a><span data-ttu-id="dfe01-277">手順 4: 完全なパッケージをビルドします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-277">Step 4: Build a Full Package</span></span>  
 <span data-ttu-id="dfe01-278">JD Edwards のパッケージのビルド プロセスの制限のための環境を BTSREL 更新を適用するまたは更新プログラム パッケージのビルドが正常に動作しない完全なパッケージをビルドします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-278">Because of a limitation of the JD Edwards package-build process, build a full package for the environments to which you applied the BTSREL update, or the update package build does not work correctly.</span></span> <span data-ttu-id="dfe01-279">フル パッケージ ビルドをビルドする方法については、JD Edwards のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfe01-279">See the JD Edwards documentation on how to build a full package build.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dfe01-280">JD Edwards OneWorld の ASU/ESU を適用した場合、ASU/ESU では通常新しいライブラリとビジネス関数は作成されません。</span><span class="sxs-lookup"><span data-stu-id="dfe01-280">When you apply JD Edwards OneWorld ASU/ESUs, the ASU/ESU does not typically create new library and business functions.</span></span> <span data-ttu-id="dfe01-281">そのため、プロセスは単純な。 ただし、BizTalk Adapter for JD Edwards OneWorld のカスタム パッケージは、新しいライブラリを作成します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-281">Therefore, the process is simple: however, the BizTalk Adapter for JD Edwards OneWorld custom package creates a new library.</span></span> <span data-ttu-id="dfe01-282">そのため、追加の手順を実行する必要がありますなど、手動でディレクトリを作成し、フル パッケージ ビルドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-282">Therefore, you must perform extra steps, such as manually create a directory and run a full package build.</span></span>  
  
#### <a name="modules-list"></a><span data-ttu-id="dfe01-283">モジュールの一覧</span><span class="sxs-lookup"><span data-stu-id="dfe01-283">Modules list</span></span>  
 <span data-ttu-id="dfe01-284">BTSREL カスタム パッケージは、JD Edwards OneWorld で、次のオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-284">The BTSREL custom package creates the following objects in JD Edwards OneWorld.</span></span> <span data-ttu-id="dfe01-285">BTSREL には、メタデータを抽出するためのビジネス関数と、データ型をテストするためのカスタム関数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="dfe01-285">BTSREL contains business functions to extract metadata and custom functions to test the data types.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dfe01-286">JD Edwards OneWorld の更新プログラムには 1 つのバグがあります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-286">There is a bug in the JD Edwards OneWorld update.</span></span> <span data-ttu-id="dfe01-287">すべてのビジネスとユーザー定義関数を持っていない場合は、更新プログラム パッケージのビルドではなく、フル パッケージ ビルドを完了したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-287">If you don't have all the business and custom functions, verify that a full package build was completed, rather than an update package build.</span></span>  
>  
>  <span data-ttu-id="dfe01-288">ファイルが一覧から失われた場合 (たとえば、ACBTEST の下にはすべてがあるが、その上には何もない場合)、データ辞書 (DD) の項目が失われた可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-288">If you are missing files from the list, for example, if you have everything below ACBTEST but nothing above it, you might be missing the Data Dictionary (DD) items.</span></span> <span data-ttu-id="dfe01-289">移動できます**データ項目と作業**不足しているファイルを探します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-289">You can go to **Work With Data Items** and look for missing files.</span></span>  
>   
>  <span data-ttu-id="dfe01-290">これらは ACBCHAR01、ACBDATE01、ADBINT01、ACBMATH01、および、ACBSTR01 などの他の項目がない場合は、*プライマリ データ要素*します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-290">If you are missing other items, such as ACBCHAR01, ACBDATE01, ADBINT01, ACBMATH01, and ACBSTR01, these are the *Primary Data Elements*.</span></span> <span data-ttu-id="dfe01-291">オブジェクトをプランナーから DEV にマージすると、多数のレポートがバックグラウンドで実行されます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-291">When you merge objects from planner to DEV, many reports run in the background.</span></span> <span data-ttu-id="dfe01-292">マージのレポートを開いて、エラーを探すことができます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-292">You can open the merge reports and look for errors.</span></span> <span data-ttu-id="dfe01-293">レポートにはすべての項目が一覧表示され、エラーまたは警告なしで完了したことが示されます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-293">The reports should list all the items and indicate that they were completed without errors or warnings.</span></span> <span data-ttu-id="dfe01-294">この検証を使用すれば、すべての項目が考慮されているため、作業を続行できます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-294">With this verification, you can continue because all items are accounted for.</span></span>  
  
-   <span data-ttu-id="dfe01-295">ACBCHAR01 - 文字型 01 のテスト</span><span class="sxs-lookup"><span data-stu-id="dfe01-295">ACBCHAR01 - TEST CHAR TYPE 01</span></span>  
  
-   <span data-ttu-id="dfe01-296">ACBCUST - ACB 顧客 ID</span><span class="sxs-lookup"><span data-stu-id="dfe01-296">ACBCUST - ACB CUSTOMER ID</span></span>  
  
-   <span data-ttu-id="dfe01-297">ACBDATE01 - 日付型 01 のテスト</span><span class="sxs-lookup"><span data-stu-id="dfe01-297">ACBDATE01 - TEST DATE TYPE 01</span></span>  
  
-   <span data-ttu-id="dfe01-298">ACBDEF - ACB 関数の種類の定義</span><span class="sxs-lookup"><span data-stu-id="dfe01-298">ACBDEF - ACB FUNCTION TYPE DEFINITION</span></span>  
  
-   <span data-ttu-id="dfe01-299">ACBFCNT - ACB 関数名の一覧の数</span><span class="sxs-lookup"><span data-stu-id="dfe01-299">ACBFCNT - ACB FUNCTION NAME LIST COUNT</span></span>  
  
-   <span data-ttu-id="dfe01-300">ACBFUNC - ACB 関数名の一覧</span><span class="sxs-lookup"><span data-stu-id="dfe01-300">ACBFUNC - ACB FUNCTION NAME LIST</span></span>  
  
-   <span data-ttu-id="dfe01-301">ACBFUNCN - ACB 関数名</span><span class="sxs-lookup"><span data-stu-id="dfe01-301">ACBFUNCN - ACB FUNCTION NAME</span></span>  
  
-   <span data-ttu-id="dfe01-302">ACBINT01 - 整数型 01 のテスト</span><span class="sxs-lookup"><span data-stu-id="dfe01-302">ACBINT01 - TEST INTEGER TYPE 01</span></span>  
  
-   <span data-ttu-id="dfe01-303">ACBLIB - ブローカー ライブラリの制御</span><span class="sxs-lookup"><span data-stu-id="dfe01-303">ACBLIB - CONTROL BROKER LIBRARY</span></span>  
  
-   <span data-ttu-id="dfe01-304">ACBMATH01 - 数学型 01 のテスト</span><span class="sxs-lookup"><span data-stu-id="dfe01-304">ACBMATH01 - TEST MATH TYPE 01</span></span>  
  
-   <span data-ttu-id="dfe01-305">ACBNEWS - ACB の新しいステータス</span><span class="sxs-lookup"><span data-stu-id="dfe01-305">ACBNEWS - ACB NEW STATUS</span></span>  
  
-   <span data-ttu-id="dfe01-306">ACBORDER - ACB 注文番号</span><span class="sxs-lookup"><span data-stu-id="dfe01-306">ACBORDER - ACB ORDER NUMBER</span></span>  
  
-   <span data-ttu-id="dfe01-307">ACBPRC - ACB 品目の価格</span><span class="sxs-lookup"><span data-stu-id="dfe01-307">ACBPRC - ACB ITEM PRICE</span></span>  
  
-   <span data-ttu-id="dfe01-308">ACBPROD - ACB 製品 ID</span><span class="sxs-lookup"><span data-stu-id="dfe01-308">ACBPROD - ACB PRODUCT ID</span></span>  
  
-   <span data-ttu-id="dfe01-309">ACBQTY - ACB 品目の数量</span><span class="sxs-lookup"><span data-stu-id="dfe01-309">ACBQTY - ACB ITEM QUANTITY</span></span>  
  
-   <span data-ttu-id="dfe01-310">ACBRES - ACB 結果のインジケーター</span><span class="sxs-lookup"><span data-stu-id="dfe01-310">ACBRES - ACB RESULT INDICATOR</span></span>  
  
-   <span data-ttu-id="dfe01-311">ACBSTAT - ACB ステータス</span><span class="sxs-lookup"><span data-stu-id="dfe01-311">ACBSTAT - ACB STATUS</span></span>  
  
-   <span data-ttu-id="dfe01-312">ACBSTR01 - テスト用文字列型 01</span><span class="sxs-lookup"><span data-stu-id="dfe01-312">ACBSTR01 - TEST STRING TYPE 01</span></span>  
  
-   <span data-ttu-id="dfe01-313">ACBTEST - ACB テスト画面</span><span class="sxs-lookup"><span data-stu-id="dfe01-313">ACBTEST - ACB TEST SCREEN</span></span>  
  
-   <span data-ttu-id="dfe01-314">ACBTEST2 - ACB テスト画面 2</span><span class="sxs-lookup"><span data-stu-id="dfe01-314">ACBTEST2 - ACB TEST SCREEN 2</span></span>  
  
-   <span data-ttu-id="dfe01-315">ACBTEST3 - ACB テスト画面 3</span><span class="sxs-lookup"><span data-stu-id="dfe01-315">ACBTEST3 - ACB TEST SCREEN 3</span></span>  
  
-   <span data-ttu-id="dfe01-316">B5500900 - ブローカー サポート モジュールの制御</span><span class="sxs-lookup"><span data-stu-id="dfe01-316">B5500900 - CONTROL BROKER SUPPORT MODULE</span></span>  
  
-   <span data-ttu-id="dfe01-317">D5500900 - コントロール BROKER データ構造体</span><span class="sxs-lookup"><span data-stu-id="dfe01-317">D5500900 - CONTROL BROKER DATA STRUCTURE</span></span>  
  
-   <span data-ttu-id="dfe01-318">D5500900A - コントロール BROKER データ構造体</span><span class="sxs-lookup"><span data-stu-id="dfe01-318">D5500900A - CONTROL BROKER DATA STRUCTURE</span></span>  
  
-   <span data-ttu-id="dfe01-319">D5500900B - フェッチ価格データ構造体</span><span class="sxs-lookup"><span data-stu-id="dfe01-319">D5500900B - FETCH PRICE DATA STRUCTURE</span></span>  
  
-   <span data-ttu-id="dfe01-320">D5500900C - 顧客ステータスのデータ構造の取得</span><span class="sxs-lookup"><span data-stu-id="dfe01-320">D5500900C - GET CUSTOMER STATUS DATA STRUCTURE</span></span>  
  
-   <span data-ttu-id="dfe01-321">D5500900D - 顧客ステータス データ構造体のセット</span><span class="sxs-lookup"><span data-stu-id="dfe01-321">D5500900D - SET CUSTOMER STATUS DATA STRUCTURE</span></span>  
  
-   <span data-ttu-id="dfe01-322">D5500900E - 更新プログラムの販売注文の状態データ構造体</span><span class="sxs-lookup"><span data-stu-id="dfe01-322">D5500900E - UPDATE SALES ORDER STATUS DATA STRUCTURE</span></span>  
  
-   <span data-ttu-id="dfe01-323">D5500900F - 整数のテスト</span><span class="sxs-lookup"><span data-stu-id="dfe01-323">D5500900F - TEST INTEGER</span></span>  
  
-   <span data-ttu-id="dfe01-324">D5500900G - テスト文字列</span><span class="sxs-lookup"><span data-stu-id="dfe01-324">D5500900G - TEST STRING</span></span>  
  
-   <span data-ttu-id="dfe01-325">D5500900H - 日付のテスト</span><span class="sxs-lookup"><span data-stu-id="dfe01-325">D5500900H - TEST DATE</span></span>  
  
-   <span data-ttu-id="dfe01-326">D5500900I - テスト CHAR</span><span class="sxs-lookup"><span data-stu-id="dfe01-326">D5500900I - TEST CHAR</span></span>  
  
-   <span data-ttu-id="dfe01-327">D5500900J - 数学数値のテスト</span><span class="sxs-lookup"><span data-stu-id="dfe01-327">D5500900J - TEST MATH NUMERIC</span></span>  
  
-   <span data-ttu-id="dfe01-328">D5500900K - 日付 2 のテスト</span><span class="sxs-lookup"><span data-stu-id="dfe01-328">D5500900K - TEST DATE 2</span></span>  
  
#### <a name="customize-the-jdeinteropini-file"></a><span data-ttu-id="dfe01-329">Jdeinterop.ini ファイルをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-329">Customize the jdeinterop.ini file</span></span>  
 <span data-ttu-id="dfe01-330">Connector.jar および Kernel.jar で JD Edwards OneWorld XE コネクタ クラスでは、jdeinterop.ini の構成ファイルを使用することが必要です。</span><span class="sxs-lookup"><span data-stu-id="dfe01-330">The JD Edwards OneWorld XE connector classes in Connector.jar and Kernel.jar require that you use the jdeinterop.ini configuration file.</span></span> <span data-ttu-id="dfe01-331">このファイルは、JD Edwards OneWorld ソフトウェアで定義されており、その用語を使用します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-331">This file is defined by the JD Edwards OneWorld software and uses its terminology.</span></span> <span data-ttu-id="dfe01-332">JD Edwards Interoperability Guide Release OneWorld では、目的と用語のこのファイルの詳細についてを提供可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-332">The JD Edwards Interoperability Guide Release OneWorld may provide more information about the purpose and terminology of this file.</span></span> <span data-ttu-id="dfe01-333">サンプルの jdeinterop.ini ファイルがある *< Adapter_Installation > \config\jde*します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-333">There is a sample jdeinterop.ini file in *<Adapter_Installation>\config\jde*.</span></span>  
  
<span data-ttu-id="dfe01-334">定義されているパラメーター値と一致する jdeinterop.ini の更新、**トランスポートのプロパティ**画面。</span><span class="sxs-lookup"><span data-stu-id="dfe01-334">Update jdeinterop.ini to match the parameter values that you defined in the **Transport Properties** screen.</span></span> <span data-ttu-id="dfe01-335">複数の JD Edwards OneWorld 論理システムで、それらのパラメーターに互換性がある場合は、同じ jdeinterop.ini ファイルを共有できます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-335">Multiple JD Edwards OneWorld logical systems can share the same jdeinterop.ini file if their parameters are compatible.</span></span> <span data-ttu-id="dfe01-336">一般に、2 つの論理システムは、2 つの異なる JD Edwards OneWorld コンピューター をポイントして、jdeinterop.ini の 2 つの異なるコピーが必要です。</span><span class="sxs-lookup"><span data-stu-id="dfe01-336">Generally, if two logical systems point to two different JD Edwards OneWorld computers, they need two different copies of jdeinterop.ini.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dfe01-337">Jdeinterop.ini でログ記録をオフにする必要があり、さまざまなログ ファイルのパラメーターは無視してもします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-337">The logging in jdeinterop.ini should be turned off, and the parameters for the various log files can safely be ignored.</span></span>  
  
 <span data-ttu-id="dfe01-338">次の表は、jdeinterop.ini ファイルにある各設定を項目化したものです。</span><span class="sxs-lookup"><span data-stu-id="dfe01-338">The following table itemizes the settings found in the jdeinterop.ini file.</span></span> <span data-ttu-id="dfe01-339">情報は、セクション別に構成されています。</span><span class="sxs-lookup"><span data-stu-id="dfe01-339">The information is organized by section.</span></span> <span data-ttu-id="dfe01-340">たとえば [JDENET] と各セクションは、JD Edwards OneWorld ソフトウェア内で出現する順序で一覧表示されています。</span><span class="sxs-lookup"><span data-stu-id="dfe01-340">For example [JDENET] and the sections are listed in the order that they appear in the JD Edwards OneWorld software.</span></span>  
  
#### <a name="jdeinteropini-file-settings"></a><span data-ttu-id="dfe01-341">jdeinterop.ini ファイルの設定</span><span class="sxs-lookup"><span data-stu-id="dfe01-341">jdeinterop.ini file settings</span></span>
  
|<span data-ttu-id="dfe01-342">セクション</span><span class="sxs-lookup"><span data-stu-id="dfe01-342">Section</span></span>|<span data-ttu-id="dfe01-343">パラメーターと説明</span><span class="sxs-lookup"><span data-stu-id="dfe01-343">Parameter and Description</span></span>|  
|-------------|-------------------------------|  
|<span data-ttu-id="dfe01-344">[JDENET]</span><span class="sxs-lookup"><span data-stu-id="dfe01-344">[JDENET]</span></span>|<span data-ttu-id="dfe01-345">**EnterpriseServerTimeout.**</span><span class="sxs-lookup"><span data-stu-id="dfe01-345">**EnterpriseServerTimeout.**</span></span> <span data-ttu-id="dfe01-346">エンタープライズ サーバーへの要求のタイムアウト値 (ミリ秒単位)。</span><span class="sxs-lookup"><span data-stu-id="dfe01-346">The time-out value for a request to the enterprise server in milliseconds.</span></span> <span data-ttu-id="dfe01-347">既定のサイズは 120000 です。</span><span class="sxs-lookup"><span data-stu-id="dfe01-347">The default size is 120000.</span></span><br /><br /> <span data-ttu-id="dfe01-348">**maxPoolSize.**</span><span class="sxs-lookup"><span data-stu-id="dfe01-348">**maxPoolSize.**</span></span> <span data-ttu-id="dfe01-349">JDENET ソケット接続のプール サイズ。</span><span class="sxs-lookup"><span data-stu-id="dfe01-349">The JDENET socket connection pool size.</span></span> <span data-ttu-id="dfe01-350">既定のサイズは、30 です。</span><span class="sxs-lookup"><span data-stu-id="dfe01-350">The default size is 30.</span></span>|  
|<span data-ttu-id="dfe01-351">[SERVER]</span><span class="sxs-lookup"><span data-stu-id="dfe01-351">[SERVER]</span></span>|<span data-ttu-id="dfe01-352">**glossaryTextServer.**</span><span class="sxs-lookup"><span data-stu-id="dfe01-352">**glossaryTextServer.**</span></span> <span data-ttu-id="dfe01-353">用語集のテキスト情報を提供する、エンタープライズ サーバーとポート。</span><span class="sxs-lookup"><span data-stu-id="dfe01-353">The enterprise server and port that provide glossary text information.</span></span> <span data-ttu-id="dfe01-354">これは、エラーに関する説明テキストを返すサーバーです。</span><span class="sxs-lookup"><span data-stu-id="dfe01-354">This is the server that returns text descriptions for errors.</span></span> <span data-ttu-id="dfe01-355">これは多くの場合、JD Edwards OneWorld アプリケーション サーバーと同じホストとポートです。</span><span class="sxs-lookup"><span data-stu-id="dfe01-355">This is frequently the same host and port as the JD Edwards OneWorld application server.</span></span> <span data-ttu-id="dfe01-356">別のサポート対象言語エンコード用の複数の用語集サーバーが存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-356">There may be more than one glossary server for different supported language encodings.</span></span> <span data-ttu-id="dfe01-357">たとえば、JDED:6010 または actsrv1:6009 です。</span><span class="sxs-lookup"><span data-stu-id="dfe01-357">For example, JDED:6010 or actsrv1:6009.</span></span> <span data-ttu-id="dfe01-358">これらの値は、[System Definition] \(システム定義) に設定されている値と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-358">The values must match those set in System Definition.</span></span><br /><br /> <span data-ttu-id="dfe01-359">**codePage.**</span><span class="sxs-lookup"><span data-stu-id="dfe01-359">**codePage.**</span></span> <span data-ttu-id="dfe01-360">エンコード スキームです。</span><span class="sxs-lookup"><span data-stu-id="dfe01-360">The encoding scheme.</span></span> <span data-ttu-id="dfe01-361">既定値は、1252 です。</span><span class="sxs-lookup"><span data-stu-id="dfe01-361">The default is 1252.</span></span><br /><br /> <span data-ttu-id="dfe01-362">1252 英語および西ヨーロッパ</span><span class="sxs-lookup"><span data-stu-id="dfe01-362">- 1252 English and Western European</span></span><br /><br /> <span data-ttu-id="dfe01-363">-932 日本語</span><span class="sxs-lookup"><span data-stu-id="dfe01-363">- 932 Japanese</span></span><br /><br /> <span data-ttu-id="dfe01-364">-950 繁体字中国語</span><span class="sxs-lookup"><span data-stu-id="dfe01-364">- 950 Traditional Chinese</span></span><br /><br /> <span data-ttu-id="dfe01-365">-936 簡体字中国語</span><span class="sxs-lookup"><span data-stu-id="dfe01-365">- 936 Simplified Chinese</span></span><br /><br /> <span data-ttu-id="dfe01-366">-949 韓国語</span><span class="sxs-lookup"><span data-stu-id="dfe01-366">- 949 Korean</span></span>|  
|<span data-ttu-id="dfe01-367">[ログ]</span><span class="sxs-lookup"><span data-stu-id="dfe01-367">[LOGS]</span></span>|<span data-ttu-id="dfe01-368">**log = c:\jas.log します。**</span><span class="sxs-lookup"><span data-stu-id="dfe01-368">**log= c:\jas.log.**</span></span> <span data-ttu-id="dfe01-369">ログ ファイルの場所。</span><span class="sxs-lookup"><span data-stu-id="dfe01-369">Location of the log file.</span></span> <span data-ttu-id="dfe01-370">このパラメーターは無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="dfe01-370">You can safely ignore this parameter.</span></span><br /><br /> <span data-ttu-id="dfe01-371">**debuglog = c:\jasdebug.log します。**</span><span class="sxs-lookup"><span data-stu-id="dfe01-371">**debuglog= c:\jasdebug.log.**</span></span> <span data-ttu-id="dfe01-372">デバッグ ログ ファイルの場所。</span><span class="sxs-lookup"><span data-stu-id="dfe01-372">Location of debug log file.</span></span> <span data-ttu-id="dfe01-373">このパラメーターは無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="dfe01-373">You can safely ignore this parameter.</span></span><br /><br /> <span data-ttu-id="dfe01-374">**デバッグします。**</span><span class="sxs-lookup"><span data-stu-id="dfe01-374">**Debug.**</span></span> <span data-ttu-id="dfe01-375">JDENET デバッグがオンかどうかが決定されます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-375">Determines whether JDENET debugging is on.</span></span> <span data-ttu-id="dfe01-376">既定では FALSE です。</span><span class="sxs-lookup"><span data-stu-id="dfe01-376">The default is FALSE.</span></span>|  
|<span data-ttu-id="dfe01-377">[デバッグ]</span><span class="sxs-lookup"><span data-stu-id="dfe01-377">[DEBUG]</span></span>|<span data-ttu-id="dfe01-378">**JobFile = c:\Interop.log します。**</span><span class="sxs-lookup"><span data-stu-id="dfe01-378">**JobFile= c:\Interop.log.**</span></span> <span data-ttu-id="dfe01-379">エラー ファイルの場所。</span><span class="sxs-lookup"><span data-stu-id="dfe01-379">Location of error file.</span></span> <span data-ttu-id="dfe01-380">このパラメーターは無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="dfe01-380">You can safely ignore this parameter.</span></span><br /><br /> <span data-ttu-id="dfe01-381">**DebugFile = c:\InteropDebug.log します。**</span><span class="sxs-lookup"><span data-stu-id="dfe01-381">**DebugFile= c:\InteropDebug.log.**</span></span> <span data-ttu-id="dfe01-382">デバッグ ファイルの場所。</span><span class="sxs-lookup"><span data-stu-id="dfe01-382">Location of debug file.</span></span> <span data-ttu-id="dfe01-383">このパラメーターは無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="dfe01-383">You can safely ignore this parameter.</span></span><br /><br /> <span data-ttu-id="dfe01-384">**log = c:\net.log します。**</span><span class="sxs-lookup"><span data-stu-id="dfe01-384">**log= c:\net.log.**</span></span> <span data-ttu-id="dfe01-385">ログ ファイルの場所。</span><span class="sxs-lookup"><span data-stu-id="dfe01-385">Location of log file.</span></span> <span data-ttu-id="dfe01-386">このパラメーターは無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="dfe01-386">You can safely ignore this parameter.</span></span><br /><br /> <span data-ttu-id="dfe01-387">**debugLevel = 0 - 12。**</span><span class="sxs-lookup"><span data-stu-id="dfe01-387">**debugLevel= 0 - 12.**</span></span> <span data-ttu-id="dfe01-388">デバッグ レベル。</span><span class="sxs-lookup"><span data-stu-id="dfe01-388">Debug levels.</span></span> <span data-ttu-id="dfe01-389">このパラメーターは無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="dfe01-389">You can safely ignore this parameter.</span></span> <span data-ttu-id="dfe01-390">このパラメーターでは、COM サーバーのみで、指定されたログ ファイル内の COM コネクタと Callobject コンポーネントによって提供されるトレースのレベルを定義します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-390">This defines the level of tracing provided by the COM Connector and the Callobject component in the specified log file, in the COM server only.</span></span><br /><br /> <span data-ttu-id="dfe01-391">-None は 0。</span><span class="sxs-lookup"><span data-stu-id="dfe01-391">- 0 None.</span></span> <span data-ttu-id="dfe01-392">ログ記録が無効になり、エラーのみが JobFile に書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-392">Logging is turned off and only errors are written to the JobFile.</span></span><br /><br /> <span data-ttu-id="dfe01-393">-2 つのエラー (エラー メッセージ)</span><span class="sxs-lookup"><span data-stu-id="dfe01-393">- 2 Errors (error messages)</span></span><br /><br /> <span data-ttu-id="dfe01-394">-4: システム エラー (例外メッセージ)</span><span class="sxs-lookup"><span data-stu-id="dfe01-394">- 4 System Errors (exception messages)</span></span><br /><br /> <span data-ttu-id="dfe01-395">-6: 警告情報</span><span class="sxs-lookup"><span data-stu-id="dfe01-395">- 6 Warning Information</span></span><br /><br /> <span data-ttu-id="dfe01-396">-8: 最小トレース (キー操作。</span><span class="sxs-lookup"><span data-stu-id="dfe01-396">- 8 Min Trace (Key operations.</span></span> <span data-ttu-id="dfe01-397">たとえば、ログオン、ログオフ、ビジネス関数の呼び出し。)</span><span class="sxs-lookup"><span data-stu-id="dfe01-397">For example, Logon, Logoff, Business Function calls.)</span></span><br /><br /> <span data-ttu-id="dfe01-398">-10 のトラブルシューティングの情報 (ヘルプ)。</span><span class="sxs-lookup"><span data-stu-id="dfe01-398">- 10 Troubleshooting Information (Help).</span></span><br /><br /> <span data-ttu-id="dfe01-399">-12 の完全なデバッグ情報 (すべてを記録する)</span><span class="sxs-lookup"><span data-stu-id="dfe01-399">- 12 Complete Debug Information (Logs everything)</span></span><br /><br /> <span data-ttu-id="dfe01-400">-既定では、トレースを有効にする必要はありませんが、トレースは、コードをデバッグする場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="dfe01-400">- By default, you do not have to turn on tracing, but tracing is useful when you are debugging your code.</span></span><br /><br /> <span data-ttu-id="dfe01-401">-NetTraceLevel = 0。</span><span class="sxs-lookup"><span data-stu-id="dfe01-401">- NetTraceLevel=0.</span></span> <span data-ttu-id="dfe01-402">トレース レベル。</span><span class="sxs-lookup"><span data-stu-id="dfe01-402">Trace levels.</span></span> <span data-ttu-id="dfe01-403">このパラメーターは無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="dfe01-403">You can safely ignore this parameter.</span></span> <span data-ttu-id="dfe01-404">COM サーバーのみで、指定されたログ ファイルでは、ThinNet コンポーネントによって提供されるトレースのレベルを定義します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-404">Defines the level of tracing provided by the ThinNet component in the specified log file, in the COM server only.</span></span> <span data-ttu-id="dfe01-405">奇数の値は、レベルを今後追加するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="dfe01-405">The odd values are reserved for future levels to be added.</span></span><br /><br /> <span data-ttu-id="dfe01-406">-次の一覧には、さらに多くのデバッグ レベルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-406">-  The following list describes debug levels even more:</span></span><br /><br /> <span data-ttu-id="dfe01-407">-0 トレースなし</span><span class="sxs-lookup"><span data-stu-id="dfe01-407">-     0 No trace</span></span><br /><br /> <span data-ttu-id="dfe01-408">-1 レコードのプロセス ID、スレッド ID、および新しい接続が追加され、ソケット プールが検索されるときに利用可能なソケット ステータスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfe01-408">- 1 Refers to the Record process ID, thread ID, and the available socket status when a new connection is added and the socket pool is searched.</span></span><br /><br /> <span data-ttu-id="dfe01-409">-2 では、トレース レベル 1 の情報が含まれますも、接続マネージャー クラスで行われたすべての呼び出しをトレースします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-409">- 2 Includes the information in trace level 1 and also traces every call made in the connection manager class.</span></span><br /><br /> <span data-ttu-id="dfe01-410">-3 には、トレース レベル 2、およびもトレース getPort() 呼び出しおよび getHost() 呼び出しですべての情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-410">- 3 Includes all information in trace level 2, and also traces getPort() calls and getHost() calls.</span></span>|  
|<span data-ttu-id="dfe01-411">[INTEROP]</span><span class="sxs-lookup"><span data-stu-id="dfe01-411">[INTEROP]</span></span>|<span data-ttu-id="dfe01-412">**enterpriseServer.**</span><span class="sxs-lookup"><span data-stu-id="dfe01-412">**enterpriseServer.**</span></span> <span data-ttu-id="dfe01-413">この値は、ホスト サーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="dfe01-413">This value is the name of the host server.</span></span> <span data-ttu-id="dfe01-414">この値が同じ値で入力するかどうかを確認、**ホスト名**フィールドに、 **JDE 資格情報**セクション**システム定義**で、 **トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="dfe01-414">Make sure that this value is the same value that you enter in the **Host Name** field in the **JDE Credentials** section in **System Definition** in the **Transport Properties** dialog box.</span></span> <span data-ttu-id="dfe01-415">既定では JDED です。</span><span class="sxs-lookup"><span data-stu-id="dfe01-415">The default is JDED.</span></span><br /><br /> <span data-ttu-id="dfe01-416">**ポート。**</span><span class="sxs-lookup"><span data-stu-id="dfe01-416">**port.**</span></span> <span data-ttu-id="dfe01-417">この値は、データの交換に使用されるポート番号です。</span><span class="sxs-lookup"><span data-stu-id="dfe01-417">This value is the port number that is used to exchange data.</span></span> <span data-ttu-id="dfe01-418">この値が同じ値で入力するかどうかを確認、**ポート番号**フィールドに、JD Edwards**資格情報**セクション、**トランスポートのプロパティ、システム定義**.</span><span class="sxs-lookup"><span data-stu-id="dfe01-418">Make sure that this value is the same value that you enter in the **Port Number** field in the JD Edwards **Credentials** section in the **Transport Properties, System Definition**.</span></span> <span data-ttu-id="dfe01-419">たとえば、6010 や 6009 です。</span><span class="sxs-lookup"><span data-stu-id="dfe01-419">For example, 6010 or 6009.</span></span> <span data-ttu-id="dfe01-420">設定された値が一致する必要があります**システム定義**します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-420">The values must match those set in **System Definition**.</span></span><br /><br /> <span data-ttu-id="dfe01-421">**inactive_timeout**します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-421">**inactive_timeout**.</span></span> <span data-ttu-id="dfe01-422">自動コミット モードのトランザクションのタイムアウト値 (ミリ秒単位)。</span><span class="sxs-lookup"><span data-stu-id="dfe01-422">The time-out value in milliseconds for a transaction in auto-commit mode.</span></span> <span data-ttu-id="dfe01-423">ユーザーがこの時間 (ミリ秒単位) の間アクティブでなかった場合は、相互運用サーバーによってそのユーザーがログオフされます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-423">If the user is inactive for this period of time (in milliseconds), the interop server logs off the user.</span></span> <span data-ttu-id="dfe01-424">この値は、より短い時間に変更できます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-424">You can change this value to a shorter period of time.</span></span> <span data-ttu-id="dfe01-425">既定では 1200000 です。</span><span class="sxs-lookup"><span data-stu-id="dfe01-425">The default is 1200000.</span></span><br /><br /> <span data-ttu-id="dfe01-426">**manual_timeout します。**</span><span class="sxs-lookup"><span data-stu-id="dfe01-426">**manual_timeout.**</span></span> <span data-ttu-id="dfe01-427">手動コミット モードでのトランザクションのミリ秒のタイムアウト値。</span><span class="sxs-lookup"><span data-stu-id="dfe01-427">The time-out value in milliseconds for a transaction in manual commit mode.</span></span> <span data-ttu-id="dfe01-428">既定では 120000 です。</span><span class="sxs-lookup"><span data-stu-id="dfe01-428">The default is 120000.</span></span><br /><br /> <span data-ttu-id="dfe01-429">**リポジトリ。**</span><span class="sxs-lookup"><span data-stu-id="dfe01-429">**Repository.**</span></span> <span data-ttu-id="dfe01-430">Connector.jar と Kernel.jar が含まれたディレクトリの場所を指します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-430">Points to the location of the directory that contains Connector.jar and Kernel.jar.</span></span> <span data-ttu-id="dfe01-431">UNIX では、これは完全なパスです。</span><span class="sxs-lookup"><span data-stu-id="dfe01-431">On UNIX, this is a full path.</span></span>|  
|<span data-ttu-id="dfe01-432">[CORBA]</span><span class="sxs-lookup"><span data-stu-id="dfe01-432">[CORBA]</span></span>|<span data-ttu-id="dfe01-433">このパラメーターは無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="dfe01-433">You can safely ignore this parameter.</span></span><br /><br /> <span data-ttu-id="dfe01-434">**マルチ スレッドです。**</span><span class="sxs-lookup"><span data-stu-id="dfe01-434">**Multithread.**</span></span> <span data-ttu-id="dfe01-435">設定は無視できます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-435">The setting can be ignored.</span></span> <span data-ttu-id="dfe01-436">CORBA でマルチスレッド サポートの場合は 1 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-436">Set to 1 for multithread support for CORBA.</span></span><br /><br /> <span data-ttu-id="dfe01-437">Objects= CORBA::Connector;CORBA::OneWorldVersion</span><span class="sxs-lookup"><span data-stu-id="dfe01-437">Objects= CORBA::Connector;CORBA::OneWorldVersion</span></span><br /><br /> <span data-ttu-id="dfe01-438">CORBA サーバーで起動時に作成するオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-438">Defines the objects for the CORBA server to create at startup.</span></span> <span data-ttu-id="dfe01-439">-DIORFILENAME が置き換えられますコマンド ライン オプションをたとえば =: CORBA::Connector=connector.ior します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-439">Also replaces the -DIORFILENAME = command-line option, for example: CORBA::Connector=connector.ior.</span></span>|  
  
## <a name="jd-edwards-enterpriseone"></a><span data-ttu-id="dfe01-440">JD Edwards EnterpriseOne</span><span class="sxs-lookup"><span data-stu-id="dfe01-440">JD Edwards EnterpriseOne</span></span>  
<span data-ttu-id="dfe01-441">このセクションでには、BizTalk Server と JD Edwards EnterpriseOne の Microsoft BizTalk Adapter の使用に関する重要な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="dfe01-441">This sections includes key information on using the Microsoft BizTalk Adapter for JD Edwards EnterpriseOne with BizTalk Server.</span></span>
  
### <a name="execute-a-jd-edwards-enterpriseone-master-business-function"></a><span data-ttu-id="dfe01-442">JD Edwards EnterpriseOne のマスター ビジネス関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-442">Execute a JD Edwards EnterpriseOne master business function</span></span>  
 <span data-ttu-id="dfe01-443">BizTalk Adapter for JD Edwards EnterpriseOne を使用して、住所録、購買オーダー、受注オーダーなどの JD Edwards EnterpriseOne のマスター ビジネス関数を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-443">You can use the BizTalk Adapter for JD Edwards EnterpriseOne to invoke a JD Edwards EnterpriseOne master business function, such as Address Book, Purchase Order, or Sales Order.</span></span> <span data-ttu-id="dfe01-444">このアダプターは、JD Edwards EnterpriseOne を BizTalk Server と接続するための統合作業の一部として使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-444">You can also use the adapter as part of an integration effort to connect JD Edwards EnterpriseOne with BizTalk Server.</span></span>  
  
##### <a name="access-data-stored-in-jd-edwards-enterpriseone"></a><span data-ttu-id="dfe01-445">JD Edwards EnterpriseOne に格納されているデータにアクセス</span><span class="sxs-lookup"><span data-stu-id="dfe01-445">Access data stored in JD Edwards EnterpriseOne</span></span>  
 <span data-ttu-id="dfe01-446">このアダプターでは、BizTalk Server アプリケーションで次のいずれかを使用して、JD Edwards EnterpriseOne との通信およびトランザクションの交換を可能にするために、XML メッセージを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-446">The adapter accepts XML messages to enable BizTalk Server applications to communicate and exchange transactions with JD Edwards EnterpriseOne using one of the following:</span></span>  
  
-   <span data-ttu-id="dfe01-447">**送信アダプター**、JD Edwards EnterpriseOne にメッセージを送信する静的な送信請求-応答の送信ポートを使用し、応答が必要です。</span><span class="sxs-lookup"><span data-stu-id="dfe01-447">**Transmit Adapter**, which uses a Static Solicit-Response Send port to send a message to JD Edwards EnterpriseOne and expects a response.</span></span>    
-   <span data-ttu-id="dfe01-448">**受信アダプター**、静的な一方向の受信ポートを使用する JD Edwards EnterpriseOne からメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-448">**Receive Adapter**, which uses a Static One-Way Receive port to receive messages from JD Edwards EnterpriseOne.</span></span>  
  
### <a name="interoperability-framework"></a><span data-ttu-id="dfe01-449">相互運用性フレームワーク</span><span class="sxs-lookup"><span data-stu-id="dfe01-449">Interoperability framework</span></span>  
 <span data-ttu-id="dfe01-450">JD Edwards EnterpriseOne では、その相互運用性フレームワークを通じて各システムとの統合に備えます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-450">JD Edwards EnterpriseOne provides for integration with systems through its interoperability framework.</span></span> <span data-ttu-id="dfe01-451">アダプターでは、JD Edwards EnterpriseOne のフレームワークを使用して、さまざまな統合、最大限の柔軟性と機能を提供するアクセス メソッドを利用しています。</span><span class="sxs-lookup"><span data-stu-id="dfe01-451">The adapter uses the JD Edwards EnterpriseOne framework, and takes advantage of various integration access methods to provide the greatest amount of flexibility and functionality.</span></span>  
  
 <span data-ttu-id="dfe01-452">BizTalk Adapter for JD Edwards EnterpriseOne では、次の統合アクセス方法がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="dfe01-452">BizTalk Adapter for JD Edwards EnterpriseOne supports the following integration access methods:</span></span>  
  
- <span data-ttu-id="dfe01-453">JD Edwards EnterpriseOne ThinNet API</span><span class="sxs-lookup"><span data-stu-id="dfe01-453">JD Edwards EnterpriseOne ThinNet API</span></span>    
- <span data-ttu-id="dfe01-454">JD Edwards EnterpriseOne XML</span><span class="sxs-lookup"><span data-stu-id="dfe01-454">JD Edwards EnterpriseOne XML</span></span>    
- <span data-ttu-id="dfe01-455">JD Edwards EnterpriseOne の未編集トランザクション テーブル (Z テーブル)</span><span class="sxs-lookup"><span data-stu-id="dfe01-455">JD Edwards EnterpriseOne unedited transaction tables (Z tables)</span></span>  
  
  <span data-ttu-id="dfe01-456">アダプターでは、JD Edwards EnterpriseOne ThinNet API を使用して、JD Edwards EnterpriseOne アプリケーションと通信します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-456">The adapter uses the JD Edwards EnterpriseOne ThinNet API to communicate with the JD Edwards EnterpriseOne application.</span></span> <span data-ttu-id="dfe01-457">アダプターでは、ThinNet API を使用することによって、1 つの作業単位 (UOW) で 1 つのマスター ビジネス関数 (MBF) を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-457">By using the ThinNet API, the adapter can invoke one master business function (MBF) in a single unit of work (UOW).</span></span> <span data-ttu-id="dfe01-458">MBF が失敗した場合、UOW 全体が失敗します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-458">When an MBF fails, the whole UOW fails.</span></span> <span data-ttu-id="dfe01-459">これによって、部分的な更新が防止されます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-459">This prevents partial updates.</span></span> <span data-ttu-id="dfe01-460">データ、ビジネス ルール、および基になるデータベースへの通信の検証は、JD Edwards EnterpriseOne アプリケーションによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-460">The validation of data, business rules, and communications to the underlying database are handled by the JD Edwards EnterpriseOne application.</span></span>  
  
#### <a name="jd-edwards-outbound-processing-framework"></a><span data-ttu-id="dfe01-461">JD Edwards の送信処理フレームワーク</span><span class="sxs-lookup"><span data-stu-id="dfe01-461">JD Edwards Outbound Processing Framework</span></span>  
 <span data-ttu-id="dfe01-462">送信プロセスでは、特定の MBF が JD Edwards EnterpriseOne 環境で実行されると、イベントが開始します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-462">In the outbound process, the event starts when a specific MBF is executed in the JD Edwards EnterpriseOne environment.</span></span> <span data-ttu-id="dfe01-463">MBF では、このイベントに必要な情報を適切なインターフェイス テーブルに書き込んでから、イベントが発生したことをサブシステム バッチ関数 (BF) に通知します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-463">The MBF writes the required information for the event into the appropriate interface table and then notifies the subsystem batch function (BF) that an event occurred.</span></span> <span data-ttu-id="dfe01-464">次に、サブシステム BF では、イベントに関するエントリをサブシステムのデータ キューに含めます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-464">The subsystem BF then includes an entry about the event on the subsystem data queue.</span></span>  
  
 <span data-ttu-id="dfe01-465">送信サブシステムでは、データ キューのエントリを取得し、通知すべき外部プロセスがないか、データ エクスポートの制御テーブルを検索します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-465">The outbound subsystem retrieves the data queue entry and looks in the Data Export Control table for the external processes to notify.</span></span> <span data-ttu-id="dfe01-466">次に送信サブシステムでは、その通知で BizTalk Adapter for JD Edwards EnterpriseOne のリスナーを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-466">The outbound subsystem then calls the BizTalk Adapter for JD Edwards EnterpriseOne listener with notification.</span></span> <span data-ttu-id="dfe01-467">このリスナーでは、通知をジェネレーターに渡します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-467">The listener passes the notification to the generator.</span></span> <span data-ttu-id="dfe01-468">次にジェネレーターでは、JD Edwards EnterpriseOne ThinNet API を使用して、インターフェイス テーブルから適切な情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-468">The generator then uses the JD Edwards EnterpriseOne ThinNet API to retrieve the appropriate information from the interface table.</span></span>  
  
### <a name="set-string-justification-in-jdearglist"></a><span data-ttu-id="dfe01-469">Jdearglist で一連の文字列の位置</span><span class="sxs-lookup"><span data-stu-id="dfe01-469">Set string justification in Jdearglist</span></span>  
 <span data-ttu-id="dfe01-470">右揃えになり左側として特定の文字列引数を構成するには、j. d. で埋められます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-470">To configure certain string arguments as right-justified and left padded in the J.D.</span></span> <span data-ttu-id="dfe01-471">Edwards EnterpriseOne の jdearglist.txt ファイル; にアクセスするどのようなビジネス機能を知る必要があります。具体的には、呼び出したいビジネス関数のどのフィールドが必要です。</span><span class="sxs-lookup"><span data-stu-id="dfe01-471">Edwards EnterpriseOne jdearglist.txt file, you must know what business function you want to access; specifically, you must know which fields in the business function you want to call.</span></span>  
  
 <span data-ttu-id="dfe01-472">オーケストレーションでバインド (スキーマ) を生成する前に、jdearglist.txt を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-472">You must update the jdearglist.txt before you generate the bindings (schemas) in the orchestration.</span></span> <span data-ttu-id="dfe01-473">文字列値"処理"セクションに記載されている、jdearglist.txt ファイルを更新するための手順です。</span><span class="sxs-lookup"><span data-stu-id="dfe01-473">The instructions for updating the jdearglist.txt file outlined in the "Handling String Values" section.</span></span>  
  
 <span data-ttu-id="dfe01-474">ログに jdearglist.txt の警告メッセージを受信する場合、その目的は、jdearglist.txt がないことを通知するためにです。</span><span class="sxs-lookup"><span data-stu-id="dfe01-474">If you receive a jdearglist.txt warning message in the log, its purpose is to inform you that the jdearglist.txt is missing.</span></span> <span data-ttu-id="dfe01-475">ただし、SalesOrder または PurchaseOrder ビジネス関数を実行している場合、パスにそのファイルがある必要があります。 または機能しません。</span><span class="sxs-lookup"><span data-stu-id="dfe01-475">However, if you are running the SalesOrder or PurchaseOrder business function, you must have that file in your PATH or it does not work.</span></span>  
  
### <a name="understand-jdeinteropini"></a><span data-ttu-id="dfe01-476">Jdeinterop.ini を理解します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-476">Understand jdeinterop.ini</span></span>  
 <span data-ttu-id="dfe01-477">Connector.jar および Kernel.jar で JD Edwards EnterpriseOne コネクタ クラスでは、jdeinterop.ini という名前の構成ファイルを使用することが必要です。</span><span class="sxs-lookup"><span data-stu-id="dfe01-477">The JD Edwards EnterpriseOne connector classes in Connector.jar and Kernel.jar require that you use a configuration file named jdeinterop.ini.</span></span> <span data-ttu-id="dfe01-478">このファイルは、JD Edwards EnterpriseOne ソフトウェアで定義され、その用語を使用します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-478">This file is defined by the JD Edwards EnterpriseOne software and uses its terminology.</span></span> <span data-ttu-id="dfe01-479">目的と用語のこのファイルの詳細については、JD Edwards の相互運用性ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfe01-479">For more information about the purpose and terminology of this file, see the JD Edwards Interoperability Guide.</span></span> <span data-ttu-id="dfe01-480">サンプルの jdeinterop.ini ファイルがある: Program files \ Microsoft BizTalk Adapters for Enterprise applications \ j. d.</span><span class="sxs-lookup"><span data-stu-id="dfe01-480">There is a sample jdeinterop.ini file in: Program Files\ Microsoft BizTalk Adapters for Enterprise Applications\ J.D.</span></span> <span data-ttu-id="dfe01-481">Edwards EnterpriseOne(r) \config します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-481">Edwards EnterpriseOne(r)\config.</span></span>  
  
 <span data-ttu-id="dfe01-482">やり取りするために手動でこのファイルを編集することはお勧めできません、**トランスポートのプロパティ** ダイアログ ボックスの送信ポート - としてマークされているフィールドなどの **< BizTalk によって構成された\>**.</span><span class="sxs-lookup"><span data-stu-id="dfe01-482">It is not recommended that you edit this file manually because it interacts with the **Transport Properties** dialog box for the send port -- for example those fields marked as **<configured by BizTalk\>**.</span></span>  
  
## <a name="peoplesoft-enterprise"></a><span data-ttu-id="dfe01-483">PeopleSoft Enterprise</span><span class="sxs-lookup"><span data-stu-id="dfe01-483">PeopleSoft Enterprise</span></span>  
<span data-ttu-id="dfe01-484">このセクションには、BizTalk Server と PeopleSoft Enterprise の Microsoft BizTalk Adapter の使用に関する重要な情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-484">This section includes key information on using the Microsoft BizTalk Adapter for PeopleSoft Enterprise with BizTalk Server.</span></span>
  
### <a name="receive-handler-peoplesoft-requirements"></a><span data-ttu-id="dfe01-485">受信ハンドラー PeopleSoft の要件</span><span class="sxs-lookup"><span data-stu-id="dfe01-485">Receive handler PeopleSoft requirements</span></span>  
 <span data-ttu-id="dfe01-486">PeopleSoft Integration Broker が、BizTalk Server と通信可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-486">The PeopleSoft Integration Broker must be able to communicate with BizTalk Server.</span></span> <span data-ttu-id="dfe01-487">次のことが既存の PeopleSoft 環境ですでに実行済みの可能性があるため、既存のノードを再利用できる可能性があります。このため、PeopleSoft のシステム管理者から HTTP の仕様を入手する以外に何も行う必要はないかもしれません。</span><span class="sxs-lookup"><span data-stu-id="dfe01-487">The following could have already occurred in an existing PeopleSoft environment and you could reuse an existing node; therefore, you would not have to do anything except obtain the HTTP specifications from a PeopleSoft System Administrator.</span></span> <span data-ttu-id="dfe01-488">詳細については、PeopleSoft のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfe01-488">For detailed information, see the PeopleSoft documentation.</span></span>  

<span data-ttu-id="dfe01-489">次の手順では、PeopleSoft を実行する概要を提供します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-489">The following steps provide an overview to complete in PeopleSoft:</span></span>  
  
1.  <span data-ttu-id="dfe01-490">メッセージを設定し、アクティブにし、アプリケーション デザイナーを使用します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-490">Set up the message, and make it active through the Application Designer.</span></span>  
  
2.  <span data-ttu-id="dfe01-491">PeopleSoft integration.gateway.properties ファイルに対して、1 回限りの変更を行います。</span><span class="sxs-lookup"><span data-stu-id="dfe01-491">Make a one-time change to the PeopleSoft integration.gateway.properties file.</span></span>  
  
3.  <span data-ttu-id="dfe01-492">作成し、ゲートウェイと HTTP のアクティブ化するノードを構成します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-492">Create and configure the gateway and nodes to activate HTTP:</span></span>
  
    -   <span data-ttu-id="dfe01-493">ノードでは、LOCATION_SYNC メカニズムなどのなんらかのトリガー メソッドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-493">The node must be using some triggering method, for example, the LOCATION_SYNC mechanism.</span></span>   
    -   <span data-ttu-id="dfe01-494">ノードでは、HTTP を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-494">The node must use HTTP.</span></span>    
    -   <span data-ttu-id="dfe01-495">ノードでは、イベントの送信先のホストとポートを指示している必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-495">The node must point to the host and port to which you are sending the event.</span></span>  
  
### <a name="send-handler-peoplesoft-requirements"></a><span data-ttu-id="dfe01-496">送信ハンドラー PeopleSoft の要件</span><span class="sxs-lookup"><span data-stu-id="dfe01-496">Send handler PeopleSoft requirements</span></span>  
 <span data-ttu-id="dfe01-497">BizTalk Adapter for PeopleSoft Enterprise は、Java API を使用してアクセスを提供するカスタム コンポーネント インターフェイス (CI) で構成されます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-497">BizTalk Adapter for PeopleSoft Enterprise consists of a custom component interface (CI) that provides access through a Java API.</span></span> <span data-ttu-id="dfe01-498">カスタム CI オブジェクトの**GET_CI_INFO**で BizTalk Adapter for PeopleSoft Enterprise のために必要なメタデータ情報を提供する PeopleSoft ツールを使用して PeopleSoft システムにデプロイされます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-498">A custom CI object, **GET_CI_INFO**, is deployed in the PeopleSoft system using PeopleSoft Tools, to provide metadata information that is required by BizTalk Adapter for PeopleSoft Enterprise.</span></span> <span data-ttu-id="dfe01-499">詳細については、PeopleSoft のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfe01-499">For more information, refer to PeopleSoft documentation.</span></span>  
  
 <span data-ttu-id="dfe01-500">カスタム コンポーネント インターフェイスをアップロードするのは 1 回だけです。</span><span class="sxs-lookup"><span data-stu-id="dfe01-500">Uploading of the custom component interface is a one-time occurrence.</span></span> <span data-ttu-id="dfe01-501">このファイルの GET_CI_INFO.pc は製品に付属しており、アダプターを使用して CI を参照するには、PeopleSoft システムにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-501">This file, GET_CI_INFO.pc, is provided with the product and must be installed in the PeopleSoft system before you can use the adapter to browse CIs.</span></span> <span data-ttu-id="dfe01-502">PeopleSoft アプリケーション デザイナにアクセスできる必要がありますが、アプリケーション デザイナは、BizTalk Server コンピューターの近くに存在する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="dfe01-502">You must have access to the PeopleSoft Application Designer; however, the Application Designer does not have to be anywhere near the BizTalk Server computer.</span></span> <span data-ttu-id="dfe01-503">アプリケーション デザイナーを使用して、参照する PeopleSoft コンピューターにカスタム CI をアップロードします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-503">You use the Application Designer to upload the custom CI into the PeopleSoft computer that you browse.</span></span>  
  
 <span data-ttu-id="dfe01-504">環境変数 CLASSPATH を設定する必要がありますので、PeopleSoft コンピューターへのアクセスが必要 (またはその情報を設定、**トランスポートのプロパティ**ウィンドウ) PeopleSoft PSJOA/psjoa.jar ファイルを指すようにします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-504">You must have access to the PeopleSoft computer because you must set the environment variable CLASSPATH (or set the information in the **Transport Properties** window) to point to the PeopleSoft PSJOA/psjoa.jar file.</span></span>  
  
### <a name="set-environment-variable-and-use-component-interface"></a><span data-ttu-id="dfe01-505">環境変数を設定し、コンポーネント インターフェイスの使用</span><span class="sxs-lookup"><span data-stu-id="dfe01-505">Set environment variable and use component interface</span></span>  
<span data-ttu-id="dfe01-506">PeopleSoft の詳細については、PeopleSoft のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfe01-506">For more information about PeopleSoft, see the PeopleSoft documentation.</span></span>  
  
#### <a name="set-classpath-environment-variable"></a><span data-ttu-id="dfe01-507">ClassPath 環境変数な設定</span><span class="sxs-lookup"><span data-stu-id="dfe01-507">Set ClassPath environment variable</span></span>  

<span data-ttu-id="dfe01-508">**JAVA_HOME を更新します。**</span><span class="sxs-lookup"><span data-stu-id="dfe01-508">**Update JAVA_HOME**</span></span>    
  
 <span data-ttu-id="dfe01-509">たとえば、JDK のインストール をポイントする JAVA_HOME 変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-509">Set the JAVA_HOME variable to point to your JDK installation, for example:</span></span>  
  
```  
set JAVA_HOME=C:\j2sdk1.4.2_06  
```  
  
 <span data-ttu-id="dfe01-510">**CLASSPATH を更新します。**</span><span class="sxs-lookup"><span data-stu-id="dfe01-510">**Update CLASSPATH**</span></span>  
  
<span data-ttu-id="dfe01-511">使用するには、コンポーネント インターフェイス (PeopleSoft 8 のみ)、クラスパスに含める、PeopleSoft コンポーネント インターフェイスを更新する必要があります jar ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-511">To use component interfaces (PeopleSoft 8 only) you must update your CLASSPATH to include the PeopleSoft component interface jar file:</span></span>
  
1. <span data-ttu-id="dfe01-512">**コントロール パネルの **オープン**システム**します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-512">In **Control Panel**, open **System**.</span></span>  
  
2. <span data-ttu-id="dfe01-513">**詳細設定**  タブで **環境変数**、し、**クラスパス**します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-513">On the **Advanced** tab, select **Environment Variables**, and then select **CLASSPATH**.</span></span>  
  
3. <span data-ttu-id="dfe01-514">パスを追加します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-514">Add the path.</span></span> <span data-ttu-id="dfe01-515">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-515">For example, enter:</span></span>  
  
   ```  
   <PeopleSoft_Home>\web\PSJOA\psjoa.jar  
   ```  
  
   <span data-ttu-id="dfe01-516">BizTalk Adapter for PeopleSoft Enterprise では、psjoa.jar ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="dfe01-516">BizTalk Adapter for PeopleSoft Enterprise requires the psjoa.jar file.</span></span> <span data-ttu-id="dfe01-517">これは、送信ポートの作成時に実行されます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-517">This is performed when you create a send port.</span></span> <span data-ttu-id="dfe01-518">詳細については、アダプターのドキュメントの「Setting Transport Properties in PeopleSoft System」(PeopleSoft システムでのトランスポートのプロパティの設定) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfe01-518">For more information, see "Setting Transport Properties in PeopleSoft System" in the adapter documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dfe01-519">BizTalk Adapter for PeopleSoft Enterprise で正しい DLL を取得するように、これらのディレクトリの 1 つだけを PATH に保持させます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-519">Only have one of these directories in your PATH to make sure that BizTalk Adapter for PeopleSoft Enterprise picks up the correct DLLs.</span></span> <span data-ttu-id="dfe01-520">PeopleSoft の目的のバージョンに対して環境を正しくセットアップできないと、トレースが困難なエラーになるおそれがあります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-520">Failure to set up your environment correctly for the desired version of PeopleSoft could lead to errors that are difficult to trace.</span></span>  
  
#### <a name="use-component-interfaces"></a><span data-ttu-id="dfe01-521">コンポーネント インターフェイスの使用</span><span class="sxs-lookup"><span data-stu-id="dfe01-521">Use component interfaces</span></span>  
  
<a name="BKMK_CustomCI"></a>   
##### <a name="upload-a-custom-ci-into-peoplesoft"></a><span data-ttu-id="dfe01-522">PeopleSoft へのカスタム CI をアップロードします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-522">Upload a Custom CI into PeopleSoft</span></span>  
 <span data-ttu-id="dfe01-523">BizTalk Adapter for PeopleSoft Enterprise では、PeopleSoft アプリケーションに対する変更が必要です。</span><span class="sxs-lookup"><span data-stu-id="dfe01-523">BizTalk Adapter for PeopleSoft Enterprise requires a modification to the PeopleSoft application.</span></span> <span data-ttu-id="dfe01-524">コンポーネント インターフェイスを使用するには、PeopleSoft に、カスタム コンポーネント インターフェイスの GET_CI_INFO をアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-524">To use component interfaces, you must upload a custom component interface, GET_CI_INFO, into PeopleSoft.</span></span> <span data-ttu-id="dfe01-525">アダプターを使用するには、最初のセットアップ時に GET_CI_INFO をインポートする必要があるだけです。</span><span class="sxs-lookup"><span data-stu-id="dfe01-525">You only have to import GET_CI_INFO during initial setup to use the adapter.</span></span> <span data-ttu-id="dfe01-526">アダプターでは GET_CI_INFO を使用して、PeopleSoft 内の他の既存のコンポーネント インターフェイスについての情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-526">The adapter uses GET_CI_INFO to obtain information about other existing component interfaces in PeopleSoft.</span></span>  
  
 <span data-ttu-id="dfe01-527">このセクションでは、カスタム コンポーネント インターフェイスで PeopleSoft コンポーネント インターフェイスを参照することができますを手動でインポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-527">This section explains how to manually import a custom component interface that let you browse component interfaces in PeopleSoft.</span></span> <span data-ttu-id="dfe01-528">カスタム メソッドでは、コンポーネント インターフェイスがインストールされている、そのコンポーネント インターフェイスのプロパティを使用したり変更したりしないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="dfe01-528">Note that the custom methods do not use or modify any properties of the component interface that it is installed in.</span></span> <span data-ttu-id="dfe01-529">カスタム コンポーネント インターフェイスをインポートするには、次の方法のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-529">To import the custom component interface, you can use one of the following methods:</span></span>  
  
- <span data-ttu-id="dfe01-530">カスタム メソッドをインポートするためのコンポーネントを新規に作成します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-530">Create a new component to import the custom methods.</span></span>  
  
- <span data-ttu-id="dfe01-531">キーが含まれていない既存のコンポーネント (たとえば、INSTALLATION_RS) を使用します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-531">Use an existing component that contains no keys, for example, INSTALLATION_RS.</span></span>  
  
  <span data-ttu-id="dfe01-532">単純なコンポーネント インターフェイスには、キーを含めないでください。</span><span class="sxs-lookup"><span data-stu-id="dfe01-532">The simple component interface must not contain keys.</span></span> <span data-ttu-id="dfe01-533">特定のコンポーネント インターフェイスにキーが含まれているかどうかが不明な場合は、SQL クエリ ツールを使用して、次の簡潔な SQL ステートメントを実行できます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-533">If you are not sure whether a particular component interface contains keys, you can run this simple SQL statement using your SQL Query tool.</span></span> <span data-ttu-id="dfe01-534">キーのないアプリケーションのすべてのコンポーネント インターフェイスの一覧を提示します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-534">It gives you a list of all the component interfaces in your application that have no keys.</span></span>  
  
```  
select distinct BCNAME  
from PSBCITEM bc1  
where not exists  
(select 1  
from PSBCITEM bc2  
where bc1.BCNAME = bc2.BCNAME  
and bc2.BCTYPE in (1, 2))  
```  
  
 <span data-ttu-id="dfe01-535">PeopleSoft のドキュメントに従って、BizTalk Adapter for PeopleSoft Enterprise のカスタム メソッドを格納するための一意の単純なコンポーネントを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-535">You can follow PeopleSoft documentation to create a unique simple component for storing BizTalk Adapter for PeopleSoft Enterprise custom methods.</span></span> <span data-ttu-id="dfe01-536">また、既存のコンポーネント インターフェイスの 1 つを複製して、それをカスタム メソッドの格納に使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-536">You can also clone one of the pre-existing component interfaces and use it to store the custom methods.</span></span>  
  
 <span data-ttu-id="dfe01-537">GET_CI_INFO にキーがないことを確認するには、PeopleTools アプリケーション デザイナのコンポーネント インターフェイスのテスト ツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-537">To verify that your GET_CI_INFO has no keys, run the PeopleTools Application Designer Component Interface Test tool.</span></span>  
  
<a name="BKMK_NewCom"></a>   
##### <a name="create-a-new-component-interface"></a><span data-ttu-id="dfe01-538">新しいコンポーネント インターフェイスを作成します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-538">Create a new component interface</span></span>  
 <span data-ttu-id="dfe01-539">PeopleSoft、アプリケーション デザイナーを使用して、新しいコンポーネント インターフェイスを作成する次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="dfe01-539">Follow these steps to create a new component interface using the PeopleSoft, Application Designer:</span></span>
  
1. <span data-ttu-id="dfe01-540">開く、 **PeopleSoft アプリケーション デザイナ**します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-540">Open the **PeopleSoft Application Designer**.</span></span>  
  
2. <span data-ttu-id="dfe01-541">3 層の接続の種類を入力し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-541">Enter a three-tier connection type, and then click **OK**.</span></span> <span data-ttu-id="dfe01-542">たとえば、アプリケーション サーバーを一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-542">For example, select Application Server from the list.</span></span>  
  
3. <span data-ttu-id="dfe01-543">アプリケーション デザイナーでの**ファイル**メニューの **新規**します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-543">In the Application Designer, on the **File** menu, select **New**.</span></span>  
  
4. <span data-ttu-id="dfe01-544">**新規**ダイアログ ボックスで、**コンポーネント インターフェイス**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-544">In the **New** dialog box, select **Component Interface**, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="dfe01-545">**[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-545">Click **Select**.</span></span>  
  
6. <span data-ttu-id="dfe01-546">すべてのコンポーネントの一覧で、任意の単純なコンポーネントを選択します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-546">From the list of all components, select any simple component.</span></span> <span data-ttu-id="dfe01-547">たとえば、INSTALLATION_RS または作成した新しい PeopleSoft コンポーネントを選択します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-547">For example, select INSTALLATION_RS, or a new PeopleSoft component that you created.</span></span>  
  
   <span data-ttu-id="dfe01-548">カスタム メソッドがないを使用して、またはにインストールされているコンポーネント インターフェイスのプロパティを変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="dfe01-548">The custom methods do not use or modify any properties of the component interface that it is installed in.</span></span>  
  
   <span data-ttu-id="dfe01-549">この単純なコンポーネント インターフェイスでは、キーを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="dfe01-549">This simple component interface must not contain keys.</span></span> <span data-ttu-id="dfe01-550">特定のコンポーネント インターフェイスにキーが含まれているかどうかが不明な場合は、SQL クエリ ツールを使用して、次の簡潔な SQL ステートメントを実行できます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-550">If you are not sure whether a particular component interface contains keys, you can run this simple SQL statement using your SQL Query tool.</span></span> <span data-ttu-id="dfe01-551">キーのないアプリケーションのすべてのコンポーネント インターフェイスの一覧できます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-551">It gives you a list of all the component interfaces in your application that have no keys:</span></span>  
  
```  
select distinct BCNAME from PSBCITEM bc1 where not exists (select 1 from PSBCITEM bc2 where bc1.BCNAME = bc2.BCNAME and bc2.BCTYPE in (1, 2))  
```  
  
> [!NOTE]
>  <span data-ttu-id="dfe01-552">BizTalk adapter for PeopleSoft Enterprise のカスタム メソッドを格納するための一意の単純なコンポーネントを作成する PeopleSoft のドキュメントをフォローすることもできます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-552">You can also follow PeopleSoft documentation to create a unique simple component for storing custom methods for BizTalk Adapter for PeopleSoft Enterprise.</span></span>  
  
 <span data-ttu-id="dfe01-553">GET_CI_INFO にキーがないことを確認するには、PeopleTools アプリケーション デザイナのコンポーネント インターフェイスのテスト ツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-553">To verify that your GET_CI_INFO has no keys, run the PeopleTools Application Designer Component Interface Test tool.</span></span>  
  
##### <a name="check-component-interface"></a><span data-ttu-id="dfe01-554">コンポーネント インターフェイスを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dfe01-554">Check component interface</span></span>  
 <span data-ttu-id="dfe01-555">Microsoft BizTalk Adapter for PeopleSoft の GET_CI_INFO の PeopleSoft システムへのアップロードが完了しました。</span><span class="sxs-lookup"><span data-stu-id="dfe01-555">You have completed uploading the Microsoft BizTalk Adapter for PeopleSoft GET_CI_INFO into your PeopleSoft System.</span></span> <span data-ttu-id="dfe01-556">GET_CI_INFO は、ユーザー定義のカスタム コンポーネント インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="dfe01-556">The GET_CI_INFO is a user-defined custom component interface.</span></span> <span data-ttu-id="dfe01-557">このインターフェイスには、ユーザー定義メソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="dfe01-557">It contains user-defined methods.</span></span> <span data-ttu-id="dfe01-558">GET_CI_INFO コンポーネント インターフェイスを使用すれば、Microsoft アダプター ウィザードによって、PeopleSoft システム内のコンポーネント インターフェイスを参照できます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-558">The GET_CI_INFO component interface lets you browse component interfaces in your PeopleSoft system using the Microsoft Adapter Wizard.</span></span> <span data-ttu-id="dfe01-559">GET_CI_INFO を検索して展開し、そのユーザー定義メソッドを表示できます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-559">You can locate and expand GET_CI_INFO to view its user-defined methods.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dfe01-560">ユーザー定義メソッドの詳細については、アダプターのドキュメントの「PeopleSoft:: コンポーネント インターフェイス ユーザー定義メソッド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfe01-560">For more information about user-defined methods, see "PeopleSoft: Component Interface User-Defined Methods" in the adapter documentation.</span></span>  
  
##### <a name="set-the-component-interface-security"></a><span data-ttu-id="dfe01-561">コンポーネント インターフェイスのセキュリティを設定します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-561">Set the component interface security</span></span>  
 <span data-ttu-id="dfe01-562">カスタムの GET_CI_INFO PeopleSoft コンポーネント インターフェイスを PeopleSoft にインストールした後は、セキュリティ設定を設定**GetCINamespace**、 **GetDetails**、および**GetCollections**BizTalk Adapter for PeopleSoft Enterprise のメソッド。</span><span class="sxs-lookup"><span data-stu-id="dfe01-562">After you install the custom GET_CI_INFO PeopleSoft component interface on PeopleSoft, set the security settings for **GetCINamespace**, **GetDetails**, and **GetCollections** methods for BizTalk Adapter for PeopleSoft Enterprise.</span></span> <span data-ttu-id="dfe01-563">これは、カスタム コンポーネントまたはユーザー定義メソッドの作成時の標準的な手法です。</span><span class="sxs-lookup"><span data-stu-id="dfe01-563">This is standard practice when you create custom components or user-defined methods.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dfe01-564">次の手順では、サポートされているすべてのモードで、サポートされている PeopleSoft のすべてのリリースのセキュリティを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-564">The following procedure describes how to configure security for all supported releases of PeopleSoft in all supported modes.</span></span>  
>   
>  <span data-ttu-id="dfe01-565">コンポーネント インターフェイスのセキュリティを構成するには</span><span class="sxs-lookup"><span data-stu-id="dfe01-565">To configure security for the component interface</span></span>  
  
1.  <span data-ttu-id="dfe01-566">をポイント**PeopleTools**、 をポイント**セキュリティ**、 をポイント**アクセス許可とロール**、し、**アクセス許可リスト**します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-566">Point to **PeopleTools**, point to **Security**, point to **Permissions & Roles**, and then select **Permission Lists**.</span></span>  
  
2.  <span data-ttu-id="dfe01-567">**セキュリティの維持**ウィンドウで、 をクリックして**検索**、関連する選択**アクセス許可の一覧**、し、一覧から適切なハイパーリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-567">In the **Maintain Security** window, click **Search**, select the relevant **Permission List**, and then click the appropriate list hyperlink.</span></span>  
  
3.  <span data-ttu-id="dfe01-568">**アクセス許可リスト**、右側のペインが横に、右矢印をクリックして、 **sign-on Times**タブを表示する、**コンポーネント インターフェイス**タブ。</span><span class="sxs-lookup"><span data-stu-id="dfe01-568">In the **Permission List** pane on the right, click the right arrow next to the **Sign-on Times** tab to display the **Component Interfaces** tab.</span></span>  
  
4.  <span data-ttu-id="dfe01-569">をクリックして、**コンポーネント インターフェイス**タブ。</span><span class="sxs-lookup"><span data-stu-id="dfe01-569">Click the **Component Interfaces** tab.</span></span>  
  
5.  <span data-ttu-id="dfe01-570">新しい行を追加するプラス記号 (+) をクリックする、**コンポーネント インターフェイス**一覧。</span><span class="sxs-lookup"><span data-stu-id="dfe01-570">Click the plus sign (+) to add a new row to the **Component Interfaces** list.</span></span>  
  
6.  <span data-ttu-id="dfe01-571">選択、 **GET_CI_INFO**コンポーネントのインターフェイス、およびクリック**編集**します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-571">Select the **GET_CI_INFO** component interface, and then click **Edit**.</span></span>  
  
7.  <span data-ttu-id="dfe01-572">メソッドに設定する**へのフル アクセス**、 をクリックして **(すべて) のフル アクセス**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-572">To set the methods to **Full Access**, click **Full Access (All)**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="dfe01-573">一番下までスクロール、**コンポーネント インターフェイス**ウィンドウ、およびクリック**保存**します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-573">Scroll to the bottom of the **Component Interfaces** window, and then click **Save**.</span></span>  
  
##### <a name="test-the-component-interface"></a><span data-ttu-id="dfe01-574">コンポーネント インターフェイスをテストします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-574">Test the component interface</span></span>  
 <span data-ttu-id="dfe01-575">BizTalk Adapter for PeopleSoft Enterprise とともに提供される GET_CI_INFO コンポーネント インターフェイスのセキュリティの構成が完了しました。</span><span class="sxs-lookup"><span data-stu-id="dfe01-575">You have finished configuring security for the GET_CI_INFO component interface delivered with BizTalk Adapter for PeopleSoft Enterprise.</span></span> <span data-ttu-id="dfe01-576">PeopleSoft コンポーネント インターフェイスの準備が完了し、PeopleSoft コンポーネント インターフェイスを参照できます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-576">Your PeopleSoft component interface is ready, and you can browse PeopleSoft component interfaces.</span></span>  
  
 <span data-ttu-id="dfe01-577">アプリケーション デザイナでコンポーネント インターフェイスをテストするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-577">Follow these steps to test the component interface in the Application Designer.</span></span>  
  
 <span data-ttu-id="dfe01-578">コンポーネント インターフェイスをテストするには</span><span class="sxs-lookup"><span data-stu-id="dfe01-578">To test the component interface</span></span>  
  
1.  <span data-ttu-id="dfe01-579">開始、 **PeopleSoft アプリケーション デザイナ**します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-579">Start the **PeopleSoft Application Designer**.</span></span>  
  
2.  <span data-ttu-id="dfe01-580">**ファイル**メニューで、**オープン**、し、**定義コンポーネント インターフェイスを =** します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-580">On the **File** menu, point to **Open**, and then select **Definition = Component Interface**.</span></span>  
  
3.  <span data-ttu-id="dfe01-581">コンポーネント インターフェイスのリストから選択**GET_CI_INFO CI**します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-581">From the list of component interfaces, select **GET_CI_INFO CI**.</span></span>  
  
4.  <span data-ttu-id="dfe01-582">GET_CI_INFO を開いた後、コンポーネント インターフェイスの定義の右側のペイン内を右クリックし、 **Test Component Interface**します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-582">After you open GET_CI_INFO, right-click anywhere in the right pane of your component interface definition, and then select **Test Component Interface**.</span></span>  
  
<span data-ttu-id="dfe01-583">**Component Interface Tester**ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-583">The **Component Interface Tester** window opens.</span></span> <span data-ttu-id="dfe01-584">キーは一覧表示されないはずです。</span><span class="sxs-lookup"><span data-stu-id="dfe01-584">There should be no keys listed.</span></span> <span data-ttu-id="dfe01-585">GET_CI_INFO にキーが含まれる場合、または別のオプションの選択がある場合は、デザイナーに戻り、アプリケーション、および GET_CI_INFO からすべてのキーを削除します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-585">If your GET_CI_INFO contains keys, or if there is another option for selection, return to the Application Designer, and eliminate all keys from GET_CI_INFO.</span></span>  
  
## <a name="install-steps"></a><span data-ttu-id="dfe01-586">インストール手順</span><span class="sxs-lookup"><span data-stu-id="dfe01-586">Install steps</span></span>
 <span data-ttu-id="dfe01-587">インストールする前に BizTalk Server のことを確認して、アダプターのすべてのソフトウェア前提条件がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="dfe01-587">Before you install, be sure BizTalk Server and all the software prerequisites for the adapters are installed.</span></span> <span data-ttu-id="dfe01-588">Setup を実行する前に、すべてのアプリケーションを閉じることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-588">It is recommended that you close all applications before running Setup.</span></span>  
  
1.  <span data-ttu-id="dfe01-589">BizTalk Server を実行**Setup.exe**を選択します**Microsoft BizTalk アダプターのインストール**、選択と**Microsoft BizTalk Adapters for Enterprise Applications インストール**します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-589">Run the BizTalk Server **Setup.exe**, select **Install Microsoft BizTalk Adapters**, and select **Install Microsoft BizTalk Adapters for Enterprise Applications**.</span></span>  
  
    > [!NOTE]
    >  - <span data-ttu-id="dfe01-590">次のコマンドを使用して、サイレント インストールを実行することもできます。: msiexec/i < msi\> /qn/l \* < logfile\> --場所 < ログ ファイル\>は省略可能ではインストールの失敗が発生した場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="dfe01-590">You can also run a silent installation using the following command: msiexec /i <msi\> /qn /l\* <logfile\> -- where <logfile\> is optional, but is useful in the event of a failed installation.</span></span>  
    >  - <span data-ttu-id="dfe01-591">このインストールでは、PATH 環境変数が更新されます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-591">The installation updates the PATH environment variable.</span></span> <span data-ttu-id="dfe01-592">正しい変数を使用していることを確認するには、インストールのコマンド ウィンドウを閉じて、変数を更新します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-592">To make sure that you are using the correct variables, close the installation command window to update your variables.</span></span>  
  
2.  <span data-ttu-id="dfe01-593">そのまま使用、**使用許諾契約書**を選択し、**次**します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-593">Accept the **License Agreement**, and select **Next**.</span></span>
  
3.  <span data-ttu-id="dfe01-594">入力、**顧客情報**を選択し、**次**します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-594">Enter your **Customer Information**, and select **Next**.</span></span>  
  
4.  <span data-ttu-id="dfe01-595">選択、**完了**または**カスタム**インストール。</span><span class="sxs-lookup"><span data-stu-id="dfe01-595">Select a **Complete** or **Custom** installation:</span></span> 
  
    -   <span data-ttu-id="dfe01-596">**完全な**: Microsoft BizTalk Adapters for Enterprise Applications、すべてのプログラム機能がインストールされ、開発と実行時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-596">**Complete**: Installs all the Microsoft BizTalk Adapters for Enterprise Applications, all the program features, and is used for development and run time.</span></span>  
  
    -   <span data-ttu-id="dfe01-597">**カスタム**: アダプターと機能をインストールしてがインストールされているを選択します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-597">**Custom**: You choose the adapters and features that you want to install, and where they are installed.</span></span>  
  
    <span data-ttu-id="dfe01-598">対象を設定するには、次のように選択します。**参照**、し、インストール パスを設定します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-598">To set the destination, select **Browse**, and set the installation path.</span></span>  
  
    <span data-ttu-id="dfe01-599">選択**次**を続行します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-599">Select **Next** to continue.</span></span>  
  
5. <span data-ttu-id="dfe01-600">**インストール**、選択と**完了**を完了するとします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-600">**Install**, and select **Finish** when complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dfe01-601">インストール中に、次のエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-601">You may encounter the following error during installation:</span></span>  
>   
>  `Error 1609. An error occurred while applying security settings. CREATOR OWNER is not a valid user or group`  
>   
>  <span data-ttu-id="dfe01-602">このエラーを回避するには、次の操作をインストールを再実行します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-602">To work around this error, do the following, and run the installation again:</span></span>  
>   
>  1. <span data-ttu-id="dfe01-603">コマンド プロンプトを開く</span><span class="sxs-lookup"><span data-stu-id="dfe01-603">Open a command prompt</span></span>
>  2. <span data-ttu-id="dfe01-604">型:`net user "CREATOR OWNER" /add`します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-604">Type: `net user "CREATOR OWNER" /add`.</span></span> <span data-ttu-id="dfe01-605">これは、CREATOR OWNER と呼ばれる新しいユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-605">This creates a new user called CREATOR OWNER.</span></span>
>  3. <span data-ttu-id="dfe01-606">型:`net localgroup Users /add`します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-606">Type: `net localgroup Users /add`.</span></span> <span data-ttu-id="dfe01-607">これは、ユーザーと呼ばれる新しいグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-607">This creates a new group called Users.</span></span>
  
<span data-ttu-id="dfe01-608">BizTalk Server にアダプターを追加するには、このトピックの「BizTalk 管理者へのアダプターの追加」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfe01-608">To add the adapters to BizTalk Server, see "Add adapters to BizTalk Admin" in this topic.</span></span>

## <a name="add-adapters-to-biztalk-admin"></a><span data-ttu-id="dfe01-609">BizTalk 管理者にアダプターを追加します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-609">Add adapters to BizTalk Admin</span></span>
  
> [!NOTE]
>  <span data-ttu-id="dfe01-610">(ランタイムのみのインストールを 1 台のコンピューター、および他のコンピューター管理ツールのみのインストール) を複数コンピューター環境に BizTalk をインストールする場合、両方のコンピューターで for Enterprise Applications の BizTalk アダプターをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-610">If you install BizTalk in a multicomputer environment (runtime-only installation on one computer, and an administration tools-only installation on another computer),  you should install the BizTalk Adapters for Enterprise Applications on both the computers.</span></span>  
  
1.  <span data-ttu-id="dfe01-611">BizTalk Server 管理コンソールを開き、展開**Microsoft BizTalk Server**、順に展開**プラットフォームの設定**します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-611">Open the BizTalk Server Administration Console, expand **Microsoft BizTalk Server**, and then expand **Platform Settings**.</span></span>  
  
2.  <span data-ttu-id="dfe01-612">右クリックして**アダプター**を選択します**新規**、し、**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-612">Right-click **Adapters**, select **New**, and then select **Adapter**.</span></span>  
  
3.  <span data-ttu-id="dfe01-613">などの名前を入力します**PeopleSoft**します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-613">Enter a name, such as **PeopleSoft**.</span></span>  
  
4.  <span data-ttu-id="dfe01-614">入力した名前を選択、**アダプター**一覧**OK**します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-614">Select the name you entered from the **Adapter** list, and select **OK**.</span></span>  
   
## <a name="post-install---jd-edwards-oneworld"></a><span data-ttu-id="dfe01-615">インストール後、JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="dfe01-615">Post-install - JD Edwards OneWorld</span></span>  
 <span data-ttu-id="dfe01-616">Microsoft BizTalk Adapter for JD Edwards OneWorld は、サポートされているデータベースおよびサーバー システムと Microsoft BizTalk Server とのインターフェイスとなる送信アダプターで構成されています。</span><span class="sxs-lookup"><span data-stu-id="dfe01-616">Microsoft BizTalk Adapter for JD Edwards OneWorld consists of a transmit adapter that interfaces supported databases and server systems to Microsoft BizTalk Server.</span></span> <span data-ttu-id="dfe01-617">送信アダプターでは、BizTalk Server からサーバー システムの呼び出しを起動することができます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-617">The transmit adapter enables you to invoke a server system's call from BizTalk Server.</span></span> <span data-ttu-id="dfe01-618">送信アダプター (BizTalk Server 管理の送信ハンドラー) の構成では、SQL データベースの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-618">The transmit adapter (the BizTalk Server Administration Send Handler) configuration specifies the location of the SQL database.</span></span>  
  
 <span data-ttu-id="dfe01-619">BizTalk Adapter for JD Edwards OneWorld の使用方法、およびそのモデルと BizTalk Server モデル間のマッピングについては、アダプターのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfe01-619">See the adapter documentation for information about how to use BizTalk Adapter for JD Edwards OneWorld and about the mapping between its model and the BizTalk Server model.</span></span>  
  
### <a name="single-sign-on"></a><span data-ttu-id="dfe01-620">シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="dfe01-620">Single Sign-On</span></span>  
 <span data-ttu-id="dfe01-621">BizTalk Adapter for JD Edwards OneWorld のエンタープライズ シングル サインオン (SSO) のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-621">BizTalk Adapter for JD Edwards OneWorld provides support for Enterprise Single Sign-On (SSO).</span></span> <span data-ttu-id="dfe01-622">SSO の使用を選択した場合、**トランスポートのプロパティ** ページで、資格情報は SSO 資格情報データベース内の関連アプリケーションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-622">If you select to use SSO in the **Transport Properties** page, the credentials for the affiliate application in the SSO Credentials database are used.</span></span> <span data-ttu-id="dfe01-623">関連アプリケーションとは、資格情報を必要とするバック エンドのアプリケーションを表しています。</span><span class="sxs-lookup"><span data-stu-id="dfe01-623">An affiliate application represents an application—a back-end that requires credentials.</span></span>  
  
### <a name="installed-components"></a><span data-ttu-id="dfe01-624">インストールされているコンポーネント</span><span class="sxs-lookup"><span data-stu-id="dfe01-624">Installed components</span></span>  

* <span data-ttu-id="dfe01-625">アダプターのインストールでは、インストールして、グローバル アセンブリ キャッシュ (GAC) に、次のコンポーネントを登録します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-625">The adapter installation installs and registers the following components in the global assembly cache (GAC).</span></span> <span data-ttu-id="dfe01-626">エクスプ ローラーでアセンブリ フォルダーを開くことで、登録を確認することができます (< %windir% > \assembly) を使用して、または、 `gacutil /l` Visual Studio コマンド プロンプトから。</span><span class="sxs-lookup"><span data-stu-id="dfe01-626">You can verify the registration by opening the assembly folder in your explorer (<%WINDIR%>\assembly), or use the `gacutil /l` from the Visual Studio command prompt:</span></span>

    -   <span data-ttu-id="dfe01-627">Microsoft.BizTalk.Adapters.BizUtil.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-627">Microsoft.BizTalk.Adapters.BizUtil.dll</span></span>    
    -   <span data-ttu-id="dfe01-628">Microsoft.BizTalk.Adapters.JDEProperties.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-628">Microsoft.BizTalk.Adapters.JDEProperties.dll</span></span>    
    -   <span data-ttu-id="dfe01-629">Microsoft.BizTalk.Adapters.CoreManagement.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-629">Microsoft.BizTalk.Adapters.CoreManagement.dll</span></span>    
    -   <span data-ttu-id="dfe01-630">Microsoft.BizTalk.Adapters.CoreReceiver.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-630">Microsoft.BizTalk.Adapters.CoreReceiver.dll</span></span>    
    -   <span data-ttu-id="dfe01-631">Microsoft.BizTalk.Adapters.CoreTransmitter.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-631">Microsoft.BizTalk.Adapters.CoreTransmitter.dll</span></span>  

  
* <span data-ttu-id="dfe01-632">btsTask.exe がインストールされ、展開、`Microsoft.BizTalk.Adapters.JDEProperties.dll`ファイルを GAC にします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-632">btsTask.exe installs and deploys the `Microsoft.BizTalk.Adapters.JDEProperties.dll` file to the GAC.</span></span> <span data-ttu-id="dfe01-633">BizTalk Server の展開ログの結果は*\Program Files\Microsoft BizTalk Adapters for Enterprise applications \jdedeploy.html*と**jdeDeploy.xml**します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-633">The BizTalk Server deployment log results are in *\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\jdeDeploy.html* and **jdeDeploy.xml**.</span></span>
  
* <span data-ttu-id="dfe01-634">アダプターに固有のファイルがインストールされている*Program Files*と*Program files \common Files*します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-634">Adapter-specific files are installed in *Program Files* and *Program Files\Common Files*.</span></span>  
  
* <span data-ttu-id="dfe01-635">`sdk\`にインストールされている*Program の files \microsoft BizTalk Adapters for Enterprise applications \ j. d.Edwards OneWorld(r)* します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-635">The `sdk\` is installed in *Program Files\Microsoft BizTalk Adapters for Enterprise Applications\ J.D. Edwards OneWorld(r)*.</span></span>
  
* <span data-ttu-id="dfe01-636">* プログラム Enterprise Applications\JD Edwards OneWorld(r) を \microsoft BizTalk Adapters\*次のファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="dfe01-636">*Program Files\Microsoft BizTalk Adapters for Enterprise Applications\JD Edwards OneWorld(r)\* contains the following files:</span></span>  
  
    -   <span data-ttu-id="dfe01-637">classes\JDEJAccess.jar</span><span class="sxs-lookup"><span data-stu-id="dfe01-637">classes\JDEJAccess.jar</span></span>    
    -   <span data-ttu-id="dfe01-638">Config\ j. d.</span><span class="sxs-lookup"><span data-stu-id="dfe01-638">Config\ J.D.</span></span> <span data-ttu-id="dfe01-639">Edwards OneWorld(r) \BTSREL.exe</span><span class="sxs-lookup"><span data-stu-id="dfe01-639">Edwards OneWorld(r) \BTSREL.exe</span></span>    
    -   <span data-ttu-id="dfe01-640">Config\ j. d.</span><span class="sxs-lookup"><span data-stu-id="dfe01-640">Config\ J.D.</span></span> <span data-ttu-id="dfe01-641">Edwards OneWorld(r) \jdearglist.txt</span><span class="sxs-lookup"><span data-stu-id="dfe01-641">Edwards OneWorld(r) \jdearglist.txt</span></span>    
    -   <span data-ttu-id="dfe01-642">Config\ j. d.</span><span class="sxs-lookup"><span data-stu-id="dfe01-642">Config\ J.D.</span></span> <span data-ttu-id="dfe01-643">Edwards OneWorld(r) \jdeinterop.ini</span><span class="sxs-lookup"><span data-stu-id="dfe01-643">Edwards OneWorld(r) \jdeinterop.ini</span></span>  
  
* <span data-ttu-id="dfe01-644">* プログラムの files \common files \microsoft BizTalk Adapters for Enterprise applications \bin\*次のファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="dfe01-644">*Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\Bin\* contains the following files:</span></span>  
  
    -   <span data-ttu-id="dfe01-645">Microsoft.BizTalk.Adapters.JDEProperties.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-645">Microsoft.BizTalk.Adapters.JDEProperties.dll</span></span>    
    -   <span data-ttu-id="dfe01-646">jdecba.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-646">jdecba.dll</span></span>  
  
## <a name="post-install---jd-edwards-enterpriseone"></a><span data-ttu-id="dfe01-647">インストール後、JD Edwards EnterpriseOne</span><span class="sxs-lookup"><span data-stu-id="dfe01-647">Post-install - JD Edwards EnterpriseOne</span></span>  
 <span data-ttu-id="dfe01-648">Microsoft の BizTalk Adapter for JD Edwards EnterpriseOne には、サポートされているデータベースと BizTalk Server にサーバー システムとやり取りする送信アダプターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="dfe01-648">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne contains a transmit adapter that interfaces with supported databases and server systems to BizTalk Server.</span></span> <span data-ttu-id="dfe01-649">送信アダプターを使用すると、BizTalk Server からサーバー システムの呼び出しを起動することができます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-649">The transmit adapter enables you to invoke a server system’s call from BizTalk Server.</span></span>  
  
 <span data-ttu-id="dfe01-650">BizTalk Adapter for JD Edwards EnterpriseOne のエンタープライズ シングル サインオン (SSO) のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-650">BizTalk Adapter for JD Edwards EnterpriseOne provides support for Enterprise Single Sign-On (SSO).</span></span> <span data-ttu-id="dfe01-651">SSO の使用を選択した場合、**トランスポートのプロパティ** ページで、資格情報は SSO 資格情報データベース内の関連アプリケーションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-651">If you select to use SSO in the **Transport Properties** page, the credentials for the affiliate application in the SSO Credentials database are used.</span></span> <span data-ttu-id="dfe01-652">関連アプリケーションとは、資格情報を必要とするバック エンドのアプリケーションを表しています。</span><span class="sxs-lookup"><span data-stu-id="dfe01-652">An affiliate application represents an application—a back-end that requires credentials.</span></span>  
  
### <a name="installed-components"></a><span data-ttu-id="dfe01-653">インストールされているコンポーネント</span><span class="sxs-lookup"><span data-stu-id="dfe01-653">Installed components</span></span>  
* <span data-ttu-id="dfe01-654">アダプターのインストールでは、インストールして、グローバル アセンブリ キャッシュ (GAC) に、次のコンポーネントを登録します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-654">The adapter installation installs and registers the following components in the global assembly cache (GAC).</span></span> <span data-ttu-id="dfe01-655">エクスプ ローラーでアセンブリ フォルダーを開くことで、登録を確認することができます (< %windir% > \assembly) を使用して、または、 `gacutil /l` Visual Studio コマンド プロンプトから。</span><span class="sxs-lookup"><span data-stu-id="dfe01-655">You can verify the registration by opening the assembly folder in your explorer (<%WINDIR%>\assembly), or use the `gacutil /l` from the Visual Studio command prompt:</span></span>
  
    -   <span data-ttu-id="dfe01-656">Microsoft.BizTalk.Adapters.BizUtil.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-656">Microsoft.BizTalk.Adapters.BizUtil.dll</span></span>    
    -   <span data-ttu-id="dfe01-657">Microsoft.BizTalk.Adapters.JDEProperties.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-657">Microsoft.BizTalk.Adapters.JDEProperties.dll</span></span>    
    -   <span data-ttu-id="dfe01-658">Microsoft.BizTalk.Adapters.CoreManagement.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-658">Microsoft.BizTalk.Adapters.CoreManagement.dll</span></span>    
    -   <span data-ttu-id="dfe01-659">Microsoft.BizTalk.Adapters.CoreReceiver.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-659">Microsoft.BizTalk.Adapters.CoreReceiver.dll</span></span>    
    -   <span data-ttu-id="dfe01-660">Microsoft.BizTalk.Adapters.CoreTransmitter.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-660">Microsoft.BizTalk.Adapters.CoreTransmitter.dll</span></span>    

* <span data-ttu-id="dfe01-661">アダプターに固有のファイルがインストールされている、 *Program files \common files \microsoft BizTalk Adapters for Enterprise applications \bin*フォルダー。</span><span class="sxs-lookup"><span data-stu-id="dfe01-661">The adapter-specific files are installed in the *Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\Bin* folder.</span></span> <span data-ttu-id="dfe01-662">このフォルダーには、次のファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="dfe01-662">This folder contains the following files:</span></span>  
  
    -   <span data-ttu-id="dfe01-663">Jdecba.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-663">Jdecba.dll</span></span>    
    -   <span data-ttu-id="dfe01-664">Microsoft.BizTalk.Adapters.JDEProperties.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-664">Microsoft.BizTalk.Adapters.JDEProperties.dll</span></span>  
  
* <span data-ttu-id="dfe01-665">次のファイルがインストールされている*Enterprise applications \j.d. の Program files \microsoft BizTalk Adapters します。Edwards enterpriseone (r)*:</span><span class="sxs-lookup"><span data-stu-id="dfe01-665">The following files are installed in *Program Files\Microsoft BizTalk Adapters for Enterprise Applications\J.D. Edwards EnterpriseOne(r)*:</span></span>  
  
    -   <span data-ttu-id="dfe01-666">Bin\BTAJDEEnterpriseOneTrace.cmd</span><span class="sxs-lookup"><span data-stu-id="dfe01-666">Bin\BTAJDEEnterpriseOneTrace.cmd</span></span>    
    -   <span data-ttu-id="dfe01-667">Classes\JDEDynAccess.jar</span><span class="sxs-lookup"><span data-stu-id="dfe01-667">Classes\JDEDynAccess.jar</span></span>    
    -   <span data-ttu-id="dfe01-668">Config\btaJDEEnterpriseOneTrace.mof</span><span class="sxs-lookup"><span data-stu-id="dfe01-668">Config\btaJDEEnterpriseOneTrace.mof</span></span>    
    -   <span data-ttu-id="dfe01-669">Config\jdearglist.txt</span><span class="sxs-lookup"><span data-stu-id="dfe01-669">Config\jdearglist.txt</span></span>    
    -   <span data-ttu-id="dfe01-670">Config\jdeinterop.ini</span><span class="sxs-lookup"><span data-stu-id="dfe01-670">Config\jdeinterop.ini</span></span>    
    -   <span data-ttu-id="dfe01-671">Config\jdelog.properties</span><span class="sxs-lookup"><span data-stu-id="dfe01-671">Config\jdelog.properties</span></span>    
    -   <span data-ttu-id="dfe01-672">Sdk</span><span class="sxs-lookup"><span data-stu-id="dfe01-672">Sdk</span></span>  
  
 
## <a name="post-install---peoplesoft-enterprise"></a><span data-ttu-id="dfe01-673">インストール後の PeopleSoft Enterprise</span><span class="sxs-lookup"><span data-stu-id="dfe01-673">Post-install - PeopleSoft Enterprise</span></span>  
 <span data-ttu-id="dfe01-674">Microsoft BizTalk Adapter for PeopleSoft Enterprise には、サポートされているデータベースと BizTalk Server にシステムを server にやり取りする送信アダプターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="dfe01-674">Microsoft BizTalk Adapter for PeopleSoft Enterprise contains a transmit adapter that interfaces supported databases and server systems to BizTalk Server.</span></span> <span data-ttu-id="dfe01-675">送信アダプターを使用すると、BizTalk Server からサーバー システムの呼び出しを起動することができます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-675">The transmit adapter enables you to invoke a server system’s call from BizTalk Server.</span></span> <span data-ttu-id="dfe01-676">送信アダプター (BizTalk Server 管理の送信ハンドラー) の構成では、SQL データベースの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-676">The transmit adapter (the BizTalk Server Administration Send Handler) configuration specifies the location of the SQL database.</span></span>  
  
 <span data-ttu-id="dfe01-677">BizTalk Adapter for PeopleSoft Enterprise は、サポートのエンタープライズ シングル サインオン (SSO) を提供します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-677">BizTalk Adapter for PeopleSoft Enterprise provides support for Enterprise Single Sign-On (SSO).</span></span> <span data-ttu-id="dfe01-678">SSO の使用を選択した場合、**トランスポートのプロパティ** ページで、資格情報は SSO 資格情報データベース内の関連アプリケーションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-678">If you select to use SSO in the **Transport Properties** page, the credentials for the affiliate application in the SSO Credentials database are used.</span></span> <span data-ttu-id="dfe01-679">関連アプリケーションとは、資格情報を必要とするバック エンドのアプリケーションを表しています。</span><span class="sxs-lookup"><span data-stu-id="dfe01-679">An affiliate application represents an application—a back-end that requires credentials.</span></span>  
  
 <span data-ttu-id="dfe01-680">アダプターのインストールには、サンプルが \sdk ディレクトリに含まれています。</span><span class="sxs-lookup"><span data-stu-id="dfe01-680">The adapter installation includes samples in the \sdk directory.</span></span>  
  
### <a name="installed-components"></a><span data-ttu-id="dfe01-681">インストールされているコンポーネント</span><span class="sxs-lookup"><span data-stu-id="dfe01-681">Installed components</span></span>  
* <span data-ttu-id="dfe01-682">アダプターのインストールでは、インストールして、グローバル アセンブリ キャッシュ (GAC) に、次のコンポーネントを登録します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-682">The adapter installation installs and registers the following components in the global assembly cache (GAC).</span></span> <span data-ttu-id="dfe01-683">エクスプ ローラーでアセンブリ フォルダーを開くことで、登録を確認することができます (< %windir% > \assembly) を使用して、または、 `gacutil /l` Visual Studio コマンド プロンプトから。</span><span class="sxs-lookup"><span data-stu-id="dfe01-683">You can verify the registration by opening the assembly folder in your explorer (<%WINDIR%>\assembly), or use the `gacutil /l` from the Visual Studio command prompt:</span></span>
  
    -   <span data-ttu-id="dfe01-684">Microsoft.BizTalk.Adapters.BizUtil.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-684">Microsoft.BizTalk.Adapters.BizUtil.dll</span></span>    
    -   <span data-ttu-id="dfe01-685">Microsoft.BizTalk.Adapters.CoreManagement.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-685">Microsoft.BizTalk.Adapters.CoreManagement.dll</span></span>    
    -   <span data-ttu-id="dfe01-686">Microsoft.BizTalk.Adapters.CoreReceiver.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-686">Microsoft.BizTalk.Adapters.CoreReceiver.dll</span></span>    
    -   <span data-ttu-id="dfe01-687">Microsoft.BizTalk.Adapters.CoreTransmitter.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-687">Microsoft.BizTalk.Adapters.CoreTransmitter.dll</span></span>    

* <span data-ttu-id="dfe01-688">アダプターに固有のファイルがインストールされている*Program Files*と*Program files \common Files*します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-688">Adapter-specific files are installed in *Program Files* and *Program Files\Common Files*.</span></span> <span data-ttu-id="dfe01-689">次のファイルがインストールされている*Enterprise Applications\PeopleSoft Enterprise (r) の Program files \microsoft BizTalk Adapters*:</span><span class="sxs-lookup"><span data-stu-id="dfe01-689">The following files are installed in *Program Files\Microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise (r)*:</span></span>
  
    -   <span data-ttu-id="dfe01-690">bin\BTAPeopleSoftTrace.cmd</span><span class="sxs-lookup"><span data-stu-id="dfe01-690">bin\BTAPeopleSoftTrace.cmd</span></span>    
    -   <span data-ttu-id="dfe01-691">config\btaPeopleSoftTrace.mof</span><span class="sxs-lookup"><span data-stu-id="dfe01-691">config\btaPeopleSoftTrace.mof</span></span>    
    -   <span data-ttu-id="dfe01-692">config\GET_CI_INFO.pc</span><span class="sxs-lookup"><span data-stu-id="dfe01-692">config\GET_CI_INFO.pc</span></span>    
    -   <span data-ttu-id="dfe01-693">config\GET_CI_INFO.pc</span><span class="sxs-lookup"><span data-stu-id="dfe01-693">config\GET_CI_INFO.pc</span></span>    
    -   <span data-ttu-id="dfe01-694">sdk\\</span><span class="sxs-lookup"><span data-stu-id="dfe01-694">sdk\\</span></span>  
  
* <span data-ttu-id="dfe01-695">*プログラムの files \common files \microsoft BizTalk Adapters for Enterprise Applications*次のファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="dfe01-695">*Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications* contains the following files:</span></span>  
  
    -   <span data-ttu-id="dfe01-696">bin\psosa.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-696">bin\psosa.dll</span></span>    
    -   <span data-ttu-id="dfe01-697">bin\Microsoft.BizTalk.Adapters.CoreManagement.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-697">bin\Microsoft.BizTalk.Adapters.CoreManagement.dll</span></span>    
    -   <span data-ttu-id="dfe01-698">bin\Microsoft.BizTalk.Adapters.CoreReceiver.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-698">bin\Microsoft.BizTalk.Adapters.CoreReceiver.dll</span></span>    
    -   <span data-ttu-id="dfe01-699">bin\Microsoft.BizTalk.Adapters.CoreTransmitter.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-699">bin\Microsoft.BizTalk.Adapters.CoreTransmitter.dll</span></span>  
  
## <a name="post-install-overview---tibco-rendezvous"></a><span data-ttu-id="dfe01-700">インストール後の TIBCO Rendezvous の概要</span><span class="sxs-lookup"><span data-stu-id="dfe01-700">Post-install overview - TIBCO Rendezvous</span></span>  
 <span data-ttu-id="dfe01-701">Microsoft BizTalk Adapter に TIBCO Rendezvous が含まれています、受信し、サポートされているデータベースと BizTalk Server にサーバー システムとのインターフェイスの機能を送信します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-701">Microsoft BizTalk Adapter for TIBCO Rendezvous contains receive and transmit functionality that interface with supported databases and server systems to BizTalk Server.</span></span>  
  
- <span data-ttu-id="dfe01-702">受信側では、サーバー システムからの送信である呼び出しをリッスンします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-702">The receive side listens for calls that are outbound from the server system.</span></span>  
  
- <span data-ttu-id="dfe01-703">送信側を使用すると、BizTalk Server からサーバー システムの呼び出しを起動することができます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-703">The transmit side enables you to invoke a server system’s call from BizTalk Server.</span></span>  
  
  <span data-ttu-id="dfe01-704">Microsoft BizTalk Adapter for TIBCO Rendezvous を使用する方法について、およびそのモデルと、BizTalk Server モデル間のマッピングについて、アダプターのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfe01-704">See the adapter documentation for information about how to use Microsoft BizTalk Adapter for TIBCO Rendezvous and about the mapping between its model and the BizTalk Server model.</span></span>  
  
### <a name="installed-components"></a><span data-ttu-id="dfe01-705">インストールされているコンポーネント</span><span class="sxs-lookup"><span data-stu-id="dfe01-705">Installed components</span></span>  
* <span data-ttu-id="dfe01-706">アダプターのインストールでは、インストールして、グローバル アセンブリ キャッシュ (GAC) に、次のコンポーネントを登録します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-706">The adapter installation installs and registers the following components in the global assembly cache (GAC).</span></span> <span data-ttu-id="dfe01-707">エクスプ ローラーでアセンブリ フォルダーを開くことで、登録を確認することができます (< %windir% > \assembly) を使用して、または、 `gacutil /l` Visual Studio コマンド プロンプトから。</span><span class="sxs-lookup"><span data-stu-id="dfe01-707">You can verify the registration by opening the assembly folder in your explorer (<%WINDIR%>\assembly), or use the `gacutil /l` from the Visual Studio command prompt:</span></span> 
  
    -   <span data-ttu-id="dfe01-708">Microsoft.BizTalk.Adapters.TibcoRV</span><span class="sxs-lookup"><span data-stu-id="dfe01-708">Microsoft.BizTalk.Adapters.TibcoRV</span></span>    
    -   <span data-ttu-id="dfe01-709">Microsoft.BizTalk.Adapters.TibcoRV.Common</span><span class="sxs-lookup"><span data-stu-id="dfe01-709">Microsoft.BizTalk.Adapters.TibcoRV.Common</span></span>    
    -   <span data-ttu-id="dfe01-710">Microsoft.BizTalk.Adapters.TibcoRV.Service</span><span class="sxs-lookup"><span data-stu-id="dfe01-710">Microsoft.BizTalk.Adapters.TibcoRV.Service</span></span>    
    -   <span data-ttu-id="dfe01-711">Microsoft.BizTalk.Adapters.TibRV.Properties</span><span class="sxs-lookup"><span data-stu-id="dfe01-711">Microsoft.BizTalk.Adapters.TibRV.Properties</span></span>    
    -   <span data-ttu-id="dfe01-712">Microsoft.BizTalk.Adapters.TibcoEMS</span><span class="sxs-lookup"><span data-stu-id="dfe01-712">Microsoft.BizTalk.Adapters.TibcoEMS</span></span>    
    -   <span data-ttu-id="dfe01-713">Microsoft.BizTalk.Adapters.TibcoEMS.Properties</span><span class="sxs-lookup"><span data-stu-id="dfe01-713">Microsoft.BizTalk.Adapters.TibcoEMS.Properties</span></span>    
    -   <span data-ttu-id="dfe01-714">Microsoft.BizTalk.Adapters.TibcoRVManagement</span><span class="sxs-lookup"><span data-stu-id="dfe01-714">Microsoft.BizTalk.Adapters.TibcoRVManagement</span></span>    
    -   <span data-ttu-id="dfe01-715">Microsoft.BizTalk.Adapters.TibcoRVReceiver</span><span class="sxs-lookup"><span data-stu-id="dfe01-715">Microsoft.BizTalk.Adapters.TibcoRVReceiver</span></span>  
    -   <span data-ttu-id="dfe01-716">Microsoft.BizTalk.Adapters.TibcoRVTransmitter</span><span class="sxs-lookup"><span data-stu-id="dfe01-716">Microsoft.BizTalk.Adapters.TibcoRVTransmitter</span></span>  
  
* <span data-ttu-id="dfe01-717">アダプターに固有のファイルがインストールされている*プログラム ファイルと Program files \common Files*します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-717">Adapter-specific files are installed in *Program Files and Program Files\Common Files*.</span></span> <span data-ttu-id="dfe01-718">次のファイルがインストールされている*Enterprise applications \ TIBCO(r) Rendezvous(r) の Program files \microsoft BizTalk Adapters*:</span><span class="sxs-lookup"><span data-stu-id="dfe01-718">The following files are installed in *Program Files\Microsoft BizTalk Adapters for Enterprise Applications\ TIBCO(r) Rendezvous(r)*:</span></span>  
  
    -   <span data-ttu-id="dfe01-719">bin\BTATibcoRVTrace.cmd</span><span class="sxs-lookup"><span data-stu-id="dfe01-719">bin\BTATibcoRVTrace.cmd</span></span>    
    -   <span data-ttu-id="dfe01-720">bin\mbaRV.exe</span><span class="sxs-lookup"><span data-stu-id="dfe01-720">bin\mbaRV.exe</span></span>    
    -   <span data-ttu-id="dfe01-721">bin\Microsoft.BizTalk.Adapters.TibcoRV.Common.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-721">bin\Microsoft.BizTalk.Adapters.TibcoRV.Common.dll</span></span>    
    -   <span data-ttu-id="dfe01-722">bin\Microsoft.BizTalk.Adapters.TibcoRV.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-722">bin\Microsoft.BizTalk.Adapters.TibcoRV.dll</span></span>    
    -   <span data-ttu-id="dfe01-723">bin\Microsoft.BizTalk.Adapters.TibcoRV.Service.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-723">bin\Microsoft.BizTalk.Adapters.TibcoRV.Service.dll</span></span>    
    -   <span data-ttu-id="dfe01-724">bin\Microsoft.BizTalk.Adapters.BizUtil.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-724">bin\Microsoft.BizTalk.Adapters.BizUtil.dll</span></span>    
    -   <span data-ttu-id="dfe01-725">bin\Microsoft.BizTalk.Adapters.CoreManagement.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-725">bin\Microsoft.BizTalk.Adapters.CoreManagement.dll</span></span>    
    -   <span data-ttu-id="dfe01-726">bin\Microsoft.BizTalk.Adapters.CoreReceiver.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-726">bin\Microsoft.BizTalk.Adapters.CoreReceiver.dll</span></span>    
    -   <span data-ttu-id="dfe01-727">bin\Microsoft.BizTalk.Adapters.CoreTransmitter.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-727">bin\Microsoft.BizTalk.Adapters.CoreTransmitter.dll</span></span>    
    -   <span data-ttu-id="dfe01-728">bin\Microsoft.BizTalk.Adapters.TibRV.Properties.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-728">bin\Microsoft.BizTalk.Adapters.TibRV.Properties.dll</span></span>    
    -   <span data-ttu-id="dfe01-729">Config\btaTibcoRVTrace.mof</span><span class="sxs-lookup"><span data-stu-id="dfe01-729">Config\btaTibcoRVTrace.mof</span></span>    
    -   <span data-ttu-id="dfe01-730">sdk\\</span><span class="sxs-lookup"><span data-stu-id="dfe01-730">sdk\\</span></span>  
  
* <span data-ttu-id="dfe01-731">*プログラムの files \common files \microsoft BizTalk Adapters for Enterprise Applications*次のファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="dfe01-731">*Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications* contains the following files:</span></span>  
  
    -   <span data-ttu-id="dfe01-732">bin\tibcorvcba.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-732">bin\tibcorvcba.dll</span></span>    
    -   <span data-ttu-id="dfe01-733">Microsoft.BizTalk.Adapters.CoreManagement.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-733">Microsoft.BizTalk.Adapters.CoreManagement.dll</span></span>    
    -   <span data-ttu-id="dfe01-734">Microsoft.BizTalk.Adapters.CoreReceiver.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-734">Microsoft.BizTalk.Adapters.CoreReceiver.dll</span></span>    
    -   <span data-ttu-id="dfe01-735">Microsoft.BizTalk.Adapters.CoreTransmitter.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-735">Microsoft.BizTalk.Adapters.CoreTransmitter.dll</span></span>  
  
### <a name="add-tibcorendezvousdll-to-the-gac"></a><span data-ttu-id="dfe01-736">TIBCO を追加します。GAC に Rendezvous.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-736">Add TIBCO.Rendezvous.dll to the GAC</span></span>  
 <span data-ttu-id="dfe01-737">BizTalk Adapter for TIBCO Rendezvous が必要です、 **TIBCO します。Rendezvous.dll**ファイル。</span><span class="sxs-lookup"><span data-stu-id="dfe01-737">BizTalk Adapter for TIBCO Rendezvous requires the **TIBCO.Rendezvous.dll** file.</span></span> <span data-ttu-id="dfe01-738">必要な最小バージョンは 1.0.3036.23330 FileVersion、製品のバージョン 8.1 が付属しています。</span><span class="sxs-lookup"><span data-stu-id="dfe01-738">The minimum version that is required is 1.0.3036.23330 FileVersion, which is shipped with the product version 8.1.</span></span> <span data-ttu-id="dfe01-739">このアセンブリがインストールされていない場合、アダプターは例外をトリガーし、適切なメッセージを記録します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-739">The adapter triggers an exception and logs an appropriate message if this assembly is not installed.</span></span>  
  
 <span data-ttu-id="dfe01-740">遅延バインディングを使用して、アセンブリを読み込むときに特定のバージョンの TIBCO の TIBCO Rendezvous アセンブリが失敗しないようにする必要があります。Rendezvous.dll と TIBCO します。Rendezvous.net モジュールは、ターゲット コンピューターではありません。</span><span class="sxs-lookup"><span data-stu-id="dfe01-740">You must use late binding to load assemblies so that the TIBCO Rendezvous assemblies don't fail when a particular version of the TIBCO.Rendezvous.dll and TIBCO.Rendezvous.net module aren't on the target computer.</span></span>
  
 <span data-ttu-id="dfe01-741">**ランタイム コンポーネント**</span><span class="sxs-lookup"><span data-stu-id="dfe01-741">**Runtime Component**</span></span>  
  
 <span data-ttu-id="dfe01-742">TIBCO Rendezvous のランタイム コンポーネントがコンピューターにインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-742">Verify you have the TIBCO Rendezvous Runtime Component installed on your computer.</span></span> <span data-ttu-id="dfe01-743">ランタイム コンポーネントは、TIBCO Rendezvous のインストール時にインストールする必要がある唯一のコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="dfe01-743">The Runtime Component is the only component that you must install when you install TIBCO Rendezvous.</span></span>  

1. <span data-ttu-id="dfe01-744">Visual Studio コマンド プロンプトで、TIBCO の場所にディレクトリを変更します。Rendezvous.dll ファイルです。</span><span class="sxs-lookup"><span data-stu-id="dfe01-744">In a Visual Studio command prompt, change directories to the location of the TIBCO.Rendezvous.dll file.</span></span> <span data-ttu-id="dfe01-745">TIBCO Rendezvous の既定のインストールでは、この DLL のパスは**C:\TIBCO\TIBRV\BIN\TIBCO します。Rendezvous.dll**します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-745">The path of this DLL in the default installation of TIBCO Rendezvous is **C:\TIBCO\TIBRV\BIN\TIBCO.Rendezvous.dll**.</span></span>  
  
2. <span data-ttu-id="dfe01-746">コマンド プロンプトで、次のように入力します:</span><span class="sxs-lookup"><span data-stu-id="dfe01-746">At the command prompt, type the following:</span></span>  
  
```
C:\TIBCO\TIBRV\BIN > gacutil /i TIBCO.Rendezvous.dll
```
  
 <span data-ttu-id="dfe01-747">これにより、TIBCO.Rendezvous.dll で GAC の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-747">The TIBCO.Rendezvous.dll now shows GAC list.</span></span> <span data-ttu-id="dfe01-748">コントロール パネルで、一覧を表示するのには、開く**管理者ツール**、オープン**Microsoft .NET Framework 構成**を開き**アセンブリ キャッシュ**。</span><span class="sxs-lookup"><span data-stu-id="dfe01-748">To view the list, in Control Panel, open **Administrator Tools**, open **Microsoft .NET Framework Configuration**, and then open **Assembly Cache**.</span></span>  
  
## <a name="post-install---tibco-enterprise-message-service"></a><span data-ttu-id="dfe01-749">インストール後、TIBCO Enterprise Message Service</span><span class="sxs-lookup"><span data-stu-id="dfe01-749">Post-install - TIBCO Enterprise Message Service</span></span>  
 <span data-ttu-id="dfe01-750">Microsoft BizTalk Adapter に TIBCO Enterprise Message Service (EMS) が含まれています、受信し、サポートされているデータベースと BizTalk Server にサーバー システムとのインターフェイスの機能を送信します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-750">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) contains receive and transmit functionality that interface with supported databases and server systems to BizTalk Server.</span></span>  
  
- <span data-ttu-id="dfe01-751">受信側では、サーバー システムからの送信である呼び出しをリッスンします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-751">The receive side listens for calls that are outbound from the server system.</span></span>  

- <span data-ttu-id="dfe01-752">送信側を使用すると、BizTalk Server からサーバー システムの呼び出しを起動することができます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-752">The transmit side enables you to invoke a server system’s call from BizTalk Server.</span></span>  
  
  <span data-ttu-id="dfe01-753">BizTalk Adapter for TIBCO EMS を使用する方法について、およびそのモデルと、BizTalk Server モデル間のマッピングについて、アダプターのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfe01-753">See the adapter documentation for information about how to use BizTalk Adapter for TIBCO EMS and about the mapping between its model and the BizTalk Server model.</span></span>  
  
### <a name="installed-components"></a><span data-ttu-id="dfe01-754">インストールされているコンポーネント</span><span class="sxs-lookup"><span data-stu-id="dfe01-754">Installed components</span></span>  
* <span data-ttu-id="dfe01-755">アダプターのインストールのインストールおよび登録され、`Microsoft.BizTalk.Adapters.TibcoEMS.dll`グローバル アセンブリ キャッシュ (GAC) 内のファイル。</span><span class="sxs-lookup"><span data-stu-id="dfe01-755">The adapter installation installs and registers the `Microsoft.BizTalk.Adapters.TibcoEMS.dll` file in the global assembly cache (GAC).</span></span> <span data-ttu-id="dfe01-756">エクスプ ローラーでアセンブリ フォルダーを開くことで、登録を確認することができます (< %windir% > \assembly) を使用して、または、 `gacutil /l` Visual Studio コマンド プロンプトからです。</span><span class="sxs-lookup"><span data-stu-id="dfe01-756">You can verify the registration by opening the assembly folder in your explorer (<%WINDIR%>\assembly), or use the `gacutil /l` from the Visual Studio command prompt.</span></span>
  
* <span data-ttu-id="dfe01-757">アダプターに固有のファイルがインストールされている*Program Files*と*Program files \common Files*します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-757">Adapter-specific files are installed in *Program Files* and *Program Files\Common Files*.</span></span> <span data-ttu-id="dfe01-758">で、次のファイルがインストールされている*Enterprise Applications\TIBCO(r) Enterprise メッセージ Service(TM) の Program files \microsoft BizTalk Adapters*:</span><span class="sxs-lookup"><span data-stu-id="dfe01-758">The following files are installed under *Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Enterprise Message Service(TM)*:</span></span>  
  
    -   <span data-ttu-id="dfe01-759">bin\BTATibcoEMSTrace.cmd</span><span class="sxs-lookup"><span data-stu-id="dfe01-759">bin\BTATibcoEMSTrace.cmd</span></span>    
    -   <span data-ttu-id="dfe01-760">Microsoft.BizTalk.Adapters.TibcoEMS.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-760">Microsoft.BizTalk.Adapters.TibcoEMS.dll</span></span>    
    -   <span data-ttu-id="dfe01-761">Config\btaTibcoEMSTrace.mof</span><span class="sxs-lookup"><span data-stu-id="dfe01-761">Config\btaTibcoEMSTrace.mof</span></span>    
    -   <span data-ttu-id="dfe01-762">sdk\\</span><span class="sxs-lookup"><span data-stu-id="dfe01-762">sdk\\</span></span>  
  
* <span data-ttu-id="dfe01-763">*プログラムの files \common files \microsoft BizTalk Adapters for Enterprise applications \bin*フォルダーには、次のファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="dfe01-763">*Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\bin* folder contains the following files:</span></span>  
  
  - <span data-ttu-id="dfe01-764">Microsoft.BizTalk.Adapters.CoreManagement.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-764">Microsoft.BizTalk.Adapters.CoreManagement.dll</span></span>    
  - <span data-ttu-id="dfe01-765">Microsoft.BizTalk.Adapters.CoreReceiver.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-765">Microsoft.BizTalk.Adapters.CoreReceiver.dll</span></span>    
  - <span data-ttu-id="dfe01-766">Microsoft.BizTalk.Adapters.CoreTransmitter.dll</span><span class="sxs-lookup"><span data-stu-id="dfe01-766">Microsoft.BizTalk.Adapters.CoreTransmitter.dll</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dfe01-767">遅延バインディングを使用して、アセンブリを読み込むときに、TIBCO の特定のバージョン、TIBCO EMS のアセンブリが失敗しないようにする必要があります。EMS.dll では、ターゲット コンピューターに存在しません。</span><span class="sxs-lookup"><span data-stu-id="dfe01-767">You must use late binding to load assemblies so that the TIBCO EMS assemblies do not fail when a particular version of the TIBCO.EMS.dll is not present on the target computer.</span></span>  
  
### <a name="add-tibcoemsdll-api-to-the-gac"></a><span data-ttu-id="dfe01-768">TIBCO を追加します。GAC に EMS.dll API</span><span class="sxs-lookup"><span data-stu-id="dfe01-768">Add TIBCO.EMS.dll API to the GAC</span></span>  
 <span data-ttu-id="dfe01-769">BizTalk Adapter for TIBCO EMS では、TIBCO.EMS.dll を GAC に追加することが必要です。</span><span class="sxs-lookup"><span data-stu-id="dfe01-769">BizTalk Adapter for TIBCO EMS requires that you add the TIBCO.EMS.dll to the GAC.</span></span> <span data-ttu-id="dfe01-770">BizTalk Adapter for TIBCO EMS は、例外をトリガーし、このアセンブリがインストールされていない場合、適切なメッセージを記録します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-770">BizTalk Adapter for TIBCO EMS triggers an exception and logs an appropriate message if this assembly is not installed.</span></span>  
  
1. <span data-ttu-id="dfe01-771">TIBCO EMS C# の #API を BizTalk コンピューターにコピーします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-771">Copy the TIBCO EMS C#API to your BizTalk computer.</span></span>  
  
2. <span data-ttu-id="dfe01-772">Visual Studio コマンド プロンプトでは、c# API ファイルの場所にディレクトリを変更します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-772">In a Visual Studio command prompt, change directories to the location of the C# API file.</span></span>  
  
3. <span data-ttu-id="dfe01-773">Visual Studio コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-773">In a Visual Studio command prompt, type the following:</span></span>  
  
   ```
   C:\\<TIBCO EMS Folder\>bin> gacutil /i TIBCO.EMS.dll
   ```
  
   <span data-ttu-id="dfe01-774">これにより、TIBCO.EMS.dll が C:\Windows\assembly の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-774">The TIBCO.EMS.dll now shows in the C:\Windows\assembly listing.</span></span> <span data-ttu-id="dfe01-775">または、コントロール パネルを開きます**管理者ツール**、オープン**Microsoft .NET Framework**、開き**アセンブリ キャッシュ**GAC の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-775">Or, in Control Panel, open **Administrator Tools**, open **Microsoft .NET Framework**, and open **Assembly Cache** to view the GAC list.</span></span>  
  
   <span data-ttu-id="dfe01-776">**制限事項**</span><span class="sxs-lookup"><span data-stu-id="dfe01-776">**Limitations**</span></span>  
  
   <span data-ttu-id="dfe01-777">BizTalk Adapter for TIBCO EMS は、TIBCO を使用します。サーバーとの通信に EMS.dll します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-777">BizTalk Adapter for TIBCO EMS uses TIBCO.EMS.dll to communicate with the server.</span></span> <span data-ttu-id="dfe01-778">TIBCO.EMS.dll を使用する際の制限を次に示します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-778">The following are limitations when you use the TIBCO.EMS.dll:</span></span>  
  
4. <span data-ttu-id="dfe01-779">メッセージの圧縮は、TIBCO EMS クライアントで EMS に圧縮形式でメッセージを送信できるようには、ご利用いただけません。</span><span class="sxs-lookup"><span data-stu-id="dfe01-779">Message compression, which enables the TIBCO EMS client to send messages in a compressed form to EMS, is not available.</span></span>  
  
5. <span data-ttu-id="dfe01-780">アダプターとサーバー間のメッセージの暗号化は使用できません。</span><span class="sxs-lookup"><span data-stu-id="dfe01-780">Encryption of messages between the adapter and the server is not available.</span></span> <span data-ttu-id="dfe01-781">TIBCO.EMS.dll では、OpenSSL ライブラリを使用した SSL 暗号化は許可されませんが、アダプターでは、ProductVersion 5.0 以降で SSL がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="dfe01-781">The TIBCO.EMS.dll does not allow for SSL encryption using the OpenSSL libraries but the Adapters support the SLL with Tibco.EMS.dll with ProductVersion 5.0 and above.</span></span>  
  
6. <span data-ttu-id="dfe01-782">EMS 用の管理 API は、サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="dfe01-782">Administration API for EMS is not supported.</span></span>  
  
## <a name="adapter-tracing"></a><span data-ttu-id="dfe01-783">アダプターのトレース</span><span class="sxs-lookup"><span data-stu-id="dfe01-783">Adapter tracing</span></span>

### <a name="enable-tracing"></a><span data-ttu-id="dfe01-784">トレースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="dfe01-784">Enable tracing</span></span>
 <span data-ttu-id="dfe01-785">Windows のトレースで使用されるファイル名は、管理者が決定します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-785">The file name used with Windows tracing is up to the administrator.</span></span> <span data-ttu-id="dfe01-786">アプリケーションでは、オペレーティング システムに書き込み、特定のバックエンド システムのログが必要になるまで、すべてのログを無視します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-786">The application writes to the operating system, which ignores all logs until you want the logs for a particular back-end system.</span></span> <span data-ttu-id="dfe01-787">これを行うには、BizTalk Adapters for Enterprise Applications の別のコマンド ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-787">You do this by running a separate BizTalk Adapters for Enterprise Applications command file.</span></span> <span data-ttu-id="dfe01-788">そのコマンドの引数の 1 つは、トレース情報をキャプチャするために使用するファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="dfe01-788">One of the arguments for that command is the name of the file that is used to capture the trace information.</span></span> <span data-ttu-id="dfe01-789">詳細については、(このトピック) で「トレース イベントを使用して Windows」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfe01-789">For more information, see "Use Windows trace event" (in this topic).</span></span>
  
 <span data-ttu-id="dfe01-790">トレース ファイルをインストールする * \Program Files\Microsoft BizTalk Adapters for Enterprise Applications\*します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-790">Trace files install to *\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\*.</span></span>  
  
-   <span data-ttu-id="dfe01-791">bin\BTATrace.cmd</span><span class="sxs-lookup"><span data-stu-id="dfe01-791">bin\BTATrace.cmd</span></span>    
-   <span data-ttu-id="dfe01-792">config\btaTrace.mof</span><span class="sxs-lookup"><span data-stu-id="dfe01-792">config\btaTrace.mof</span></span>  
  
### <a name="use-windows-trace-event"></a><span data-ttu-id="dfe01-793">Windows トレース イベントを使用します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-793">Use Windows trace event</span></span>  
 <span data-ttu-id="dfe01-794">アダプターでは、エラー メッセージ、警告メッセージ、および情報メッセージを Windows イベント ビューアーに記録します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-794">The adapters log error, warning, and information messages to the Windows Event Viewer.</span></span> <span data-ttu-id="dfe01-795">その他のトレース メッセージを表示するには、Event Tracing for Windows (ETW) ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-795">You can view additional tracing messages by using the Event Tracing for Windows (ETW) tool.</span></span> <span data-ttu-id="dfe01-796">ETW が有効である場合、このメッセージを受信する \*.etl ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-796">When ETW is enabled, it creates an \*.etl file to receive the messages.</span></span> <span data-ttu-id="dfe01-797">このファイルはバイナリ形式であり、読み取るには変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-797">This file is in binary format and must be converted to be read.</span></span> <span data-ttu-id="dfe01-798">これを行うには、解釈に利用できるコンシューマー アプリケーションが必要、 \*.etl ファイル、Windows の tracerpt.exe や tracedmp.exe などです。</span><span class="sxs-lookup"><span data-stu-id="dfe01-798">To do this, you must have a consumer application available to interpret the \*.etl file, for example, Windows tracerpt.exe or tracedmp.exe.</span></span>  
  
### <a name="etw-components"></a><span data-ttu-id="dfe01-799">ETW コンポーネント</span><span class="sxs-lookup"><span data-stu-id="dfe01-799">ETW components</span></span>
  
 <span data-ttu-id="dfe01-800">Windows イベント トレーシングには 3 つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-800">Event Tracing for Windows has three components:</span></span>  
  
* <span data-ttu-id="dfe01-801">**コント ローラー アプリケーション:** にアクティブとプロバイダーを非アクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-801">**Controller application:** Activates and deactivates a provider.</span></span> <span data-ttu-id="dfe01-802">たとえば、tracelog.exe または logman.exe です。</span><span class="sxs-lookup"><span data-stu-id="dfe01-802">For example, tracelog.exe or logman.exe.</span></span>  
  
    <span data-ttu-id="dfe01-803">PATH 環境変数を、tracelog.exe の場所を指すように設定します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-803">You set your PATH environment variable to point to the location of tracelog.exe.</span></span> <span data-ttu-id="dfe01-804">これにより、BTA < アダプタ名\>トレースの呼び出しのシステムの tracelog.exe を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-804">This makes sure that BTA<Adapter Name\>Trace calls can locate tracelog.exe in the system.</span></span> <span data-ttu-id="dfe01-805">既定で BTA < アダプタ名\>トレースは、現在のパスを検索します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-805">By default, BTA<Adapter Name\>Trace searches the current path.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dfe01-806">tracelog.exe は Microsoft SDK と Microsoft BizTalk Adapters for Enterprise Applications コマンドと互換性があります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-806">tracelog.exe is available from the Microsoft SDK and is compatible with the commands provided by Microsoft BizTalk Adapters for Enterprise Applications.</span></span> <span data-ttu-id="dfe01-807">logman.exe の使い方については、logman のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfe01-807">To use logman.exe, see the logman documentation.</span></span>  
  
* <span data-ttu-id="dfe01-808">**コンシューマー アプリケーション:** 記録されたイベントの読み取り。</span><span class="sxs-lookup"><span data-stu-id="dfe01-808">**Consumer application:** Reads logged events.</span></span>  
  
    <span data-ttu-id="dfe01-809">コンシューマー アプリケーションで .etl ファイル内のイベントを読み取るには、Windows イベント トレーシングでそれらのイベントを .etl ファイルにダンプする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfe01-809">For the consumer application to be able to read the event in the .etl file, Event Tracing for Windows must dump them into that file.</span></span> <span data-ttu-id="dfe01-810">通常、この作業は、コントローラーがトレーシングを非アクティブ化するときに行われます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-810">Typically this is done when the controller deactivates the tracing.</span></span>  
  
    <span data-ttu-id="dfe01-811">コント ローラーに、コンシューマー アプリケーションを使用して、トレースを非アクティブ化せず、リアルタイムのオプションを使用してトレースをアクティブ化する必要があります **< リアルタイム\>=-rt**します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-811">To use the consumer application without deactivating the trace, the controller must activate the trace with the real-time option, **<Real time\> = -rt**.</span></span>  
  
* <span data-ttu-id="dfe01-812">**プロバイダー:** イベントを提供するために使用します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-812">**Provider:** Used to provide the event.</span></span>  
  
    <span data-ttu-id="dfe01-813">各アダプターには、5 つの異なるプロバイダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="dfe01-813">Each adapter includes five different providers.</span></span> <span data-ttu-id="dfe01-814">これらは Windows Management Instrumentation (WMI) に登録されます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-814">They are registered in Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="dfe01-815">root\WMI\EventTrace パス内で登録プロバイダーを検索するには、WMI CIM Studio などのツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-815">To find the registered providers in the root\WMI\EventTrace path, you can use tools such as WMI CIM Studio.</span></span>  
  
    <span data-ttu-id="dfe01-816">5 つのプロバイダーを使用すると、さまざまな種類のメッセージをログに記録できます。</span><span class="sxs-lookup"><span data-stu-id="dfe01-816">The five providers enable you to log different kinds of messages:</span></span>  
  
        -   **Receiver Logging Provider**: The <Trace element\> switch is - **receiver**.    
        -   **Receiver CastDetails Provider**: The <Trace element\> switch is - **castDetailsReceive**.    
        -   **Transmitter Logging Provider**: The <Trace element\> switch is - **transmitter**.    
        -   **Transmitter CastDetails Provider**: The <Trace element\> switch is - **castDetailsTransmit**.    
        -   **Management Logging Provider**: The <Trace element\> switch is - **management**.  
  
<span data-ttu-id="dfe01-817">ETW を使用するには、特定のアダプターのコマンドを実行します。`BTA<Adapter Name\>Trace.cmd`します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-817">To use ETW, run the command for the specific adapter: `BTA<Adapter Name\>Trace.cmd`.</span></span> <span data-ttu-id="dfe01-818">このコマンドは次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-818">You use this command as follows:</span></span>  
  
```  
BTA<Adapter Name>Trace <Trace element> -start [-cir <MB>|   
    -seq <MB>] [-rt] logfile  
BTA<Adapter Name>Trace <Trace element> -stop  
  
```  
  
 <span data-ttu-id="dfe01-819">各要素の説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dfe01-819">Where:</span></span>  
  
<span data-ttu-id="dfe01-820">**< トレース要素\>** プロバイダーの種類は、(必須)。</span><span class="sxs-lookup"><span data-stu-id="dfe01-820">**<Trace element\>** (required) is the kind of provider.</span></span> <span data-ttu-id="dfe01-821">使用可能なオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dfe01-821">The options are:</span></span>  
  
 <span data-ttu-id="dfe01-822">**-castDetailsTransmit**</span><span class="sxs-lookup"><span data-stu-id="dfe01-822">**-castDetailsTransmit**</span></span>  
  
 <span data-ttu-id="dfe01-823">**-送信機**</span><span class="sxs-lookup"><span data-stu-id="dfe01-823">**-transmitter**</span></span>  
  
 <span data-ttu-id="dfe01-824">**-castDetailsReceive**</span><span class="sxs-lookup"><span data-stu-id="dfe01-824">**-castDetailsReceive**</span></span>  
  
 <span data-ttu-id="dfe01-825">**-受信機**</span><span class="sxs-lookup"><span data-stu-id="dfe01-825">**-receiver**</span></span>  
  
 <span data-ttu-id="dfe01-826">**-管理**</span><span class="sxs-lookup"><span data-stu-id="dfe01-826">**-management**</span></span>  
  
 <span data-ttu-id="dfe01-827">**-開始、停止:** アクティブ化またはプロバイダーを非アクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-827">**-start, -stop:** Activate or deactivate the provider.</span></span>  
  
 <span data-ttu-id="dfe01-828">**-cir < MB\>:** サイズとファイルの種類。</span><span class="sxs-lookup"><span data-stu-id="dfe01-828">**-cir <MB\>:** Size and kind of file.</span></span> <span data-ttu-id="dfe01-829">**-cir**は循環ファイルです。</span><span class="sxs-lookup"><span data-stu-id="dfe01-829">**-cir** is a circular file.</span></span> <span data-ttu-id="dfe01-830">**< MB\>:** サイズ (メガバイト単位)。</span><span class="sxs-lookup"><span data-stu-id="dfe01-830">**<MB\>:** Size in megabytes.</span></span>  
  
 <span data-ttu-id="dfe01-831">**-seq < MB\>:** サイズとファイルの種類。</span><span class="sxs-lookup"><span data-stu-id="dfe01-831">**-seq <MB\>:** Size and kind of file.</span></span> <span data-ttu-id="dfe01-832">**-seq**はシーケンシャル ファイルです。</span><span class="sxs-lookup"><span data-stu-id="dfe01-832">**-seq** is a sequential file.</span></span> <span data-ttu-id="dfe01-833">**< MB\>:** サイズ (メガバイト単位)。</span><span class="sxs-lookup"><span data-stu-id="dfe01-833">**<MB\>:** Size in megabytes.</span></span>  
  
 <span data-ttu-id="dfe01-834">**-rt:** でリアルタイムに設定します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-834">**-rt:** Set the real-time mode on.</span></span>  
  
 <span data-ttu-id="dfe01-835">**ログ ファイル:** ログ ファイルの名前 (既定では c:\rtlog.etl) です。</span><span class="sxs-lookup"><span data-stu-id="dfe01-835">**Logfile:** Name of the log file (c:\rtlog.etl is the default).</span></span>  
  
 <span data-ttu-id="dfe01-836">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-836">For example:</span></span>  
  
```  
BTAXXXTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTAXXXTrace -transmitter -stop  
  
```  
  
> [!NOTE]
>  <span data-ttu-id="dfe01-837">.etl ファイルの書式を設定するには、tracerpt.exe コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="dfe01-837">You use the tracerpt.exe command to format the .etl files.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="dfe01-838">次のステップ</span><span class="sxs-lookup"><span data-stu-id="dfe01-838">Next steps</span></span>
* [<span data-ttu-id="dfe01-839">JD Edwards EnterpriseOne アダプター</span><span class="sxs-lookup"><span data-stu-id="dfe01-839">JD Edwards EnterpriseOne adapter</span></span>](../core/jd-edwards-enterpriseone-adapter.md)
* [<span data-ttu-id="dfe01-840">JD Edwards OneWorld アダプター</span><span class="sxs-lookup"><span data-stu-id="dfe01-840">JD Edwards OneWorld adapter</span></span>](../core/jd-edwards-oneworld-adapter.md)
* [<span data-ttu-id="dfe01-841">PeopleSoft Enterprise アダプター</span><span class="sxs-lookup"><span data-stu-id="dfe01-841">PeopleSoft Enterprise adapter</span></span>](../core/peoplesoft-enterprise-adapter.md)
* [<span data-ttu-id="dfe01-842">TIBCO Enterprise Message Service アダプター</span><span class="sxs-lookup"><span data-stu-id="dfe01-842">TIBCO Enterprise Message Service adapter</span></span>](../core/tibco-enterprise-message-service-adapter.md)
* [<span data-ttu-id="dfe01-843">TIBCO Rendezvous アダプター</span><span class="sxs-lookup"><span data-stu-id="dfe01-843">TIBCO Rendezvous adapter</span></span>](../core/tibco-rendezvous-adapter.md)
