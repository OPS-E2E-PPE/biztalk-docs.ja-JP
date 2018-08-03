---
title: Data Provider for SAP のカスタム Rfc をインストールする |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installation, custom RFCs for the Data Provider for SAP
- installing, custom RFCs for the Data Provider for SAP
- installing custom RFCs, how to
ms.assetid: 7a99db70-fa5a-4c04-9dc7-b71613d4364e
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f94bb4b6a6f094211654f5c3c0964bbf84d42f56
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989595"
---
# <a name="install-custom-rfcs-for-the-data-provider-for-sap"></a><span data-ttu-id="1d437-102">Data Provider for SAP のカスタム Rfc をインストールします。</span><span class="sxs-lookup"><span data-stu-id="1d437-102">Install Custom RFCs for the Data Provider for SAP</span></span>
<span data-ttu-id="1d437-103">MySAP Business Suite の SAP システムにアクセスする .NET Framework データ プロバイダーを使用する場合は、カスタム Rfc をインストールします。</span><span class="sxs-lookup"><span data-stu-id="1d437-103">Install the custom RFCs if you want to use the .NET Framework Data Provider for mySAP Business Suite to access the SAP system.</span></span>

<span data-ttu-id="1d437-104">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]カスタム Rfc、SAP システムにいくつかの操作を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d437-104">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requires custom RFCs to perform some operations on the SAP system to:</span></span>
  
- <span data-ttu-id="1d437-105">選択の操作を実行、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] Z_EXTRACT_DATA_OO RFC が必要です。</span><span class="sxs-lookup"><span data-stu-id="1d437-105">Run the SELECT operation, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requires Z_EXTRACT_DATA_OO RFC.</span></span>  
  
- <span data-ttu-id="1d437-106">EXECQUERY 操作を実行、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] Z_EXECUTE_SAP_QUERY RFC が必要です。</span><span class="sxs-lookup"><span data-stu-id="1d437-106">Run the EXECQUERY operation, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requires Z_EXECUTE_SAP_QUERY RFC.</span></span>  
  
<span data-ttu-id="1d437-107">SAP システムでこれらの操作を実行するには、SAP システムでこれらのカスタム Rfc をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d437-107">To perform these operations on the SAP system, you must install these custom RFCs on the SAP system.</span></span> <span data-ttu-id="1d437-108">インストールした場合、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]と共に、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]、セットアップ プログラムにコピーの RFC トランスポート、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]圧縮ファイルとして (customRFC.zip) システムでアダプターをインストールします。</span><span class="sxs-lookup"><span data-stu-id="1d437-108">If you chose to install the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] along with the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], the Setup program copies the RFC transport for the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] as a compressed file (customRFC.zip) on the system where you install the adapter.</span></span> <span data-ttu-id="1d437-109">Zip ファイルは通常にインストールされて*\<インストール ドライブ\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Microsoft .NET Framework Data Provider for mySAP Business Suite*します。</span><span class="sxs-lookup"><span data-stu-id="1d437-109">The zip file is typically installed at *\<installation drive\>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Microsoft .NET Framework Data Provider for mySAP Business Suite*.</span></span> 
  
 <span data-ttu-id="1d437-110">Zip ファイルを抽出するには、4 つのデータ ファイルが表示されます、次の名前付け、2 つのパターンを K9 *。BI1 (たとえば、K900534 に似ています。BI1)、およびその他の 2 つ R9 パターンに従う\*します。BI1 (たとえば、R900534 に似ています。BI1)。</span><span class="sxs-lookup"><span data-stu-id="1d437-110">After extracting the zip file, you will find four data files, two following the naming pattern K9*.BI1 (for example, similar to K900534.BI1), and the other two following the pattern R9\*.BI1 (for example, similar to R900534.BI1).</span></span>  
  

  
1. <span data-ttu-id="1d437-111">SAP アプリケーション サーバーに、アダプターを実行しているコンピューターから抽出したファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="1d437-111">Copy the extracted files from the computer running the adapters to the SAP application server.</span></span>  
  
   1.  <span data-ttu-id="1d437-112">開発システムの SAP アプリケーション サーバーに、SAP R/3 システムの管理者としてログインします。</span><span class="sxs-lookup"><span data-stu-id="1d437-112">Log in as the SAP R/3 system administrator to the SAP application server of your development system.</span></span>  
  
   2.  <span data-ttu-id="1d437-113">名前付けパターン K9 \* で 2 つのトランスポート ファイルをコピーします。SAP アプリケーション サーバーで、次のディレクトリに、アダプターを実行しているコンピューター上のインストール ディレクトリから BI1:</span><span class="sxs-lookup"><span data-stu-id="1d437-113">Copy the two transport files with the naming pattern K9\*.BI1 from the installation directory on the computer running the adapters to the following directory on the SAP application server:</span></span>  
  
        `<drive>:\usr\sap\trans\cofiles`  
  
   3.  <span data-ttu-id="1d437-114">名前付けパターン R9 \* で 2 つのトランスポート ファイルをコピーします。SAP アプリケーション サーバーで、次のディレクトリに、アダプターを実行しているコンピューター上のインストール ディレクトリから BI1:</span><span class="sxs-lookup"><span data-stu-id="1d437-114">Copy the two transport files with the naming pattern R9\*.BI1 from the installation directory on the computer running the adapters to the following directory on the SAP application server:</span></span>  
  
        `<drive>:\usr\sap\trans\data`  
  
2. <span data-ttu-id="1d437-115">SAP アプリケーション サーバー上のトランスポートのバッファーには、トランスポートを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="1d437-115">Load the transport into the transport buffer on the SAP application server.</span></span>  
  
   1.  <span data-ttu-id="1d437-116">コマンド プロンプトでは、SAP アプリケーション サーバー上のトランスポート プログラム ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="1d437-116">At the command prompt, navigate to the transport program directory on the SAP application server:</span></span>  
  
        `<drive>:\usr\sap\trans\bin`  
  
   2.  <span data-ttu-id="1d437-117">トランスポートのバッファーには、トランスポートを読み込むで次のコマンドを実行、`\usr\sap\trans\bin`ディレクトリと置換*sysid*開発システムのシステム id:</span><span class="sxs-lookup"><span data-stu-id="1d437-117">To load the transport into the transport buffer, execute the following command at the `\usr\sap\trans\bin` directory and replace *sysid* with the system ID of your development system:</span></span>  
  
       ```  
       tp addtobuffer <TransportNumber> <sysid> pf=TP_DOMAIN_<sysid>.PFL  
       ```  
  
        <span data-ttu-id="1d437-118">ここで、 *TransportNumber*は実際のデータ転送の数 (たとえば BI1K900534) です。</span><span class="sxs-lookup"><span data-stu-id="1d437-118">where, *TransportNumber* is the actual transport number (for example BI1K900534).</span></span>  
  
   3.  <span data-ttu-id="1d437-119">後に、`tp`コマンドが終了したら、次のようなレポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d437-119">After the `tp` command finishes, you will see a report similar to the following:</span></span>  
  
       ```  
       This is tp version 320.56.66 (release 620)  
       Addtobuffer successful for TransportNumber  
       tp finished with return code: 0  
       ```  
  
        <span data-ttu-id="1d437-120">リターン コード「0」は、操作が成功したことを意味します。</span><span class="sxs-lookup"><span data-stu-id="1d437-120">Return code "0" means that the operation succeeded.</span></span>  
  
        <span data-ttu-id="1d437-121">0 または 4 のリターン コードは、許容されます。</span><span class="sxs-lookup"><span data-stu-id="1d437-121">A return code of 0 or 4 is acceptable.</span></span> <span data-ttu-id="1d437-122">8 以降のリターン コードを受信する場合に Microsoft カスタマー サービス & サポート、お問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="1d437-122">Contact Microsoft Customer Service and Support, if you receive a return code of 8 or above.</span></span>  
  
       > [!IMPORTANT]
       >  <span data-ttu-id="1d437-123">手順 (b) と (c) をトランスポート ファイルの 2 番目のセットを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="1d437-123">Repeat steps (b) and (c) for the second set of transport files.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="1d437-124">Cofile ファイル名から実際のデータ転送の数を簡単に派生できます。</span><span class="sxs-lookup"><span data-stu-id="1d437-124">You can easily derive the actual transport number from the cofile file name.</span></span> <span data-ttu-id="1d437-125">たとえば、cofile K900534 の名前。BI1 は、BI1K900534 さまざまなトランスポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="1d437-125">For example, a cofile named K900534.BI1 provides a transport number of BI1K900534.</span></span>  
  
3. <span data-ttu-id="1d437-126">SAP トランスポートにインポートします。</span><span class="sxs-lookup"><span data-stu-id="1d437-126">Import the transport into SAP.</span></span>  
  
   1.  <span data-ttu-id="1d437-127">コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1d437-127">Execute the following command at the command prompt:</span></span>  
  
       ```  
       tp import <TransportNumber> <sysid> client=<clientnumber> pf=TP_DOMAIN_<sysid>.PFL  
       ```  
  
        <span data-ttu-id="1d437-128">置換*sysid*開発システムのシステム id。</span><span class="sxs-lookup"><span data-stu-id="1d437-128">Replace *sysid* with the system ID of your development system.</span></span> <span data-ttu-id="1d437-129">置換*clientnumber*開発システムのクライアントの数。</span><span class="sxs-lookup"><span data-stu-id="1d437-129">Replace *clientnumber* with the client number of your development system.</span></span>  
  
        <span data-ttu-id="1d437-130">次のように、以前にインストールされているオブジェクトを上書きするのに U2 パラメーターを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="1d437-130">You can use the U2 parameter to overwrite previously installed objects, as follows:</span></span>  
  
       ```  
       tp import <TransportNumber> <sysid> client=<clientnumber> U2  
       ```  
  
        <span data-ttu-id="1d437-131">または</span><span class="sxs-lookup"><span data-stu-id="1d437-131">or</span></span>  
  
       ```  
       tp import <TransportNumber> <sysid> client=<clientnumber> pf=TP_DOMAIN_<sysid>.PFL U2  
       ```  
  
       > [!NOTE]
       >  <span data-ttu-id="1d437-132">Cofile ファイル名から実際のデータ転送の数を簡単に派生できます。</span><span class="sxs-lookup"><span data-stu-id="1d437-132">You can easily derive the actual transport number from the cofile file name.</span></span> <span data-ttu-id="1d437-133">たとえば、cofile K900534 の名前。BI1 は、BI1K900534 さまざまなトランスポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="1d437-133">For example, a cofile named K900534.BI1 provides a transport number of BI1K900534.</span></span>  
  
   2.  <span data-ttu-id="1d437-134">後に、`tp`コマンドが終了したら、次のようなレポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d437-134">After the `tp` command finishes, you will see a report similar to the following:</span></span>  
  
       ```  
       This is tp version 320.56.66 (release 620)  
       This is R3trans.exe version 6.08 (release 620 - 04.02.03 - 14:54:00).  
       R3trans.exe finished (0000).  
       This is R3trans.exe version 6.08 (release 620 - 04.02.03 - 14:54:00).  
       R3trans.exe finished (0000).  
       tp finished with return code: 0  
       ```  
  
        <span data-ttu-id="1d437-135">リターン コード「0」は、操作が成功したことを意味します。</span><span class="sxs-lookup"><span data-stu-id="1d437-135">Return code "0" means that the operation succeeded.</span></span>  
  
        <span data-ttu-id="1d437-136">0 または 4 のリターン コードは、許容されます。</span><span class="sxs-lookup"><span data-stu-id="1d437-136">A return code of 0 or 4 is acceptable.</span></span> <span data-ttu-id="1d437-137">8 以降のリターン コードを受信する場合は、Microsoft カスタマー サービス & サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="1d437-137">Contact Microsoft Customer Service and Support if you receive a return code of 8 or above.</span></span>  
  
       > [!IMPORTANT]
       >  <span data-ttu-id="1d437-138">トランスポートのファイルの 2 番目のセットの手順 (a) および (b) を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="1d437-138">Repeat steps (a) and (b) for the second set of transport files.</span></span>  
  
4. <span data-ttu-id="1d437-139">トランスポート ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="1d437-139">Check the transport log.</span></span>  
  
5. <span data-ttu-id="1d437-140">SAP GUI のトランスポート オーガナイザー SE09 トランザクションを使用して、エラーがないことを検証するトランスポート ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="1d437-140">Check the transport log in SAP GUI Transport Organizer using transaction SE09 to verify that there are no errors.</span></span>  
  
   <span data-ttu-id="1d437-141">ユーザーの承認の設定</span><span class="sxs-lookup"><span data-stu-id="1d437-141">Setting User Authorization</span></span>  
   <span data-ttu-id="1d437-142">Z_EXTRACT_DATA_OO RFC では、特定の認証オブジェクトとユーザー Id が必要です。</span><span class="sxs-lookup"><span data-stu-id="1d437-142">The Z_EXTRACT_DATA_OO RFC requires user IDs with specific authorization objects.</span></span> <span data-ttu-id="1d437-143">RFC の実行に最低限の制限を設定するのにには、SAP GUI の承認管理ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="1d437-143">Use the SAP GUI authorization administration tools to set the minimum restrictions on the execution of the RFC:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1d437-144">Z_EXECUTE_SAP_QUERY RFC の承認を設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1d437-144">You do not need to set the authorization for the Z_EXECUTE_SAP_QUERY RFC.</span></span>  
  
- <span data-ttu-id="1d437-145">Z_EXTRACT_DATA_OO は S_TABU_DIS と Z_EIP_TABL の両方が必要です。</span><span class="sxs-lookup"><span data-stu-id="1d437-145">Z_EXTRACT_DATA_OO requires both S_TABU_DIS and Z_EIP_TABL.</span></span> <span data-ttu-id="1d437-146">次の値は、最小 S_TABU_DIS で、システム内の任意のテーブルのメタデータを表示できるように制限を提供します。</span><span class="sxs-lookup"><span data-stu-id="1d437-146">The following values provide the minimum restrictions for S_TABU_DIS, which allow users to view metadata for any table in the system.</span></span>  
  
  - <span data-ttu-id="1d437-147">ACTVT: 03</span><span class="sxs-lookup"><span data-stu-id="1d437-147">ACTVT: 03</span></span>  
  
  - <span data-ttu-id="1d437-148">DICBERCLS: \*</span><span class="sxs-lookup"><span data-stu-id="1d437-148">DICBERCLS: \*</span></span>  
  
    <span data-ttu-id="1d437-149">DICBERCLS を使用して、承認クラスによってテーブルに承認を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="1d437-149">You can use DICBERCLS to restrict authorization to tables by authorization class.</span></span>  
  
    <span data-ttu-id="1d437-150">TDDAT テーブルを使用すると、テーブルの承認クラスを表示します。</span><span class="sxs-lookup"><span data-stu-id="1d437-150">You can use the TDDAT table to view the authorization class for tables.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="1d437-151">テーブル メンテナンスのトランザクションによってテーブルに変更を防ぐため、運用環境での表示権限を付与する必要がありますのみ (ACTVT: 03 設定を表示する許可されたアクティビティ)。</span><span class="sxs-lookup"><span data-stu-id="1d437-151">To prevent changes to tables by table maintenance transactions, you should only grant display privileges in a production environment (ACTVT: 03 sets the permissible activity to display).</span></span>  
  
   <span data-ttu-id="1d437-152">Z_EIP_TABL の最小値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1d437-152">The minimum values for Z_EIP_TABL are:</span></span>  
  
  - <span data-ttu-id="1d437-153">ACTVT: 03</span><span class="sxs-lookup"><span data-stu-id="1d437-153">ACTVT: 03</span></span>  
  
  - <span data-ttu-id="1d437-154">テーブル: \*</span><span class="sxs-lookup"><span data-stu-id="1d437-154">TABLE: \*</span></span>  
  
    <span data-ttu-id="1d437-155">承認済みのテーブルを明示的に定義するのにテーブルを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="1d437-155">You can use TABLE to explicitly define the authorized tables.</span></span> <span data-ttu-id="1d437-156">また、S_TABU_DIS が他のトランザクションにも使用します。</span><span class="sxs-lookup"><span data-stu-id="1d437-156">Note, too, that S_TABU_DIS is also used in other transactions.</span></span>  
  
##### <a name="to-set-user-authorization"></a><span data-ttu-id="1d437-157">ユーザーの承認を設定するには</span><span class="sxs-lookup"><span data-stu-id="1d437-157">To set user authorization</span></span>  
  
1.  <span data-ttu-id="1d437-158">SAP GUI を起動します。</span><span class="sxs-lookup"><span data-stu-id="1d437-158">Start the SAP GUI.</span></span> <span data-ttu-id="1d437-159">T コードの種類に移動して`pfcg`、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1d437-159">Go to T-code, type `pfcg`, and press ENTER.</span></span>  
  
2.  <span data-ttu-id="1d437-160">**ロール**テキスト ボックスなど、作成したいロールの名前を入力`ZTEST`、 をクリックし、**ロール**します。</span><span class="sxs-lookup"><span data-stu-id="1d437-160">In the **Role** text box, enter a role name you want to create, for example, `ZTEST`, and then click **Role**.</span></span>  
  
3.  <span data-ttu-id="1d437-161">**Create Role**  ページで、をクリックして、**承認**タブ。</span><span class="sxs-lookup"><span data-stu-id="1d437-161">In the **Create Role** page, click the **Authorizations** tab.</span></span>  
  
     <span data-ttu-id="1d437-162">ロールを保存するメッセージが表示されたら、クリックして**はい**します。</span><span class="sxs-lookup"><span data-stu-id="1d437-162">If prompted to save the role, click **Yes**.</span></span>  
  
4.  <span data-ttu-id="1d437-163">**変更ロール** ページで、をクリックして、**変更承認データ**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d437-163">In the **Change Roles** page, click the **Change Authorization Data** button.</span></span>  
  
5.  <span data-ttu-id="1d437-164">テンプレートを選択するメッセージが表示されたら、**テンプレートの選択**ダイアログ ボックスで、をクリックして**テンプレートを選択しないでください**します。</span><span class="sxs-lookup"><span data-stu-id="1d437-164">If you are prompted to select a template from the **Choose Template** dialog box, click **Do not select templates**.</span></span>  
  
6.  <span data-ttu-id="1d437-165">**ロールの変更: 承認** ページで、をクリックして、**手動で**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d437-165">In the **Change role: Authorizations** page, click the **Manually** button.</span></span>  
  
7.  <span data-ttu-id="1d437-166">**承認の手動選択**承認オブジェクトの名前を入力ボックスに、 `Z_EIP_TABL` ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1d437-166">In the **Manual selection of authorizations** box, enter the name of the authorization object `Z_EIP_TABL` and press ENTER.</span></span>  
  
8.  <span data-ttu-id="1d437-167">**ロールの変更: 承認** ページで、テキスト ボックスが表示されるまでノードを展開して**アクティビティ**と**テーブル名**します。</span><span class="sxs-lookup"><span data-stu-id="1d437-167">In the **Change role: Authorizations** page, expand the nodes until you see the text boxes for **Activity** and **Table Name**.</span></span> <span data-ttu-id="1d437-168">**アクティビティ**テキスト ボックスに、値を入力`03`します。</span><span class="sxs-lookup"><span data-stu-id="1d437-168">For the **Activity** text box, enter the value `03`.</span></span> <span data-ttu-id="1d437-169">**テーブル名**テキスト ボックスに、値を入力`*`します。</span><span class="sxs-lookup"><span data-stu-id="1d437-169">For the **Table Name** text box, enter the value `*`.</span></span>  
  
9. <span data-ttu-id="1d437-170">をクリックして、**保存**プロファイルを生成するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d437-170">Click the **Save** button to generate the profile.</span></span>  
  
10. <span data-ttu-id="1d437-171">戻り、**変更ロール**ページ、をクリックし、**ユーザー**タブ。</span><span class="sxs-lookup"><span data-stu-id="1d437-171">Go back to the **Change Roles** page and click the **User** tab.</span></span>  
  
11. <span data-ttu-id="1d437-172">**ユーザー**  タブで、ユーザーの名前を入力して、ロールのユーザー ID を割り当てる、**ユーザー ID**列、およびクリック、**ユーザー比較**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d437-172">In the **User** tab, assign a user ID for the role by entering the user name in the **User ID** column, and click the **User comparison** button.</span></span>  
  
12. <span data-ttu-id="1d437-173">**ロールのユーザーのマスター レコードの比較**、 をクリックして**比較が完了**マスター レコードを更新します。</span><span class="sxs-lookup"><span data-stu-id="1d437-173">In the **Compare Role User Master Record**, click **Complete comparison** to update the master record.</span></span> <span data-ttu-id="1d437-174">ロールを保存するメッセージが表示されたら、クリックして**はい**します。</span><span class="sxs-lookup"><span data-stu-id="1d437-174">When prompted to save the role, click **Yes**.</span></span>  
  
13. <span data-ttu-id="1d437-175">保存して終了します。</span><span class="sxs-lookup"><span data-stu-id="1d437-175">Save and exit.</span></span>  
  
<span data-ttu-id="1d437-176">カスタム RFC のインストールを確認します。</span><span class="sxs-lookup"><span data-stu-id="1d437-176">Verifying Custom RFC Installation</span></span>  
 <span data-ttu-id="1d437-177">カスタム Rfc をインストールした後は、Rfc が正しくインストールされているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="1d437-177">After you install the custom RFCs, you can verify whether the RFCs installed correctly.</span></span>  
  
- <span data-ttu-id="1d437-178">Z_EXECUTE_SAP_QUERY rfc の場合は、これを行う SAP システムを使用して定義済みのクエリを実行することによって、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="1d437-178">For Z_EXECUTE_SAP_QUERY RFC, you can do so by executing a pre-defined query in SAP system using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
- <span data-ttu-id="1d437-179">Z_EXTRACT_DATA_OO の rfc は、RFC が動作するが、システムで使用できる状態であることを確認するには、次のテストを実行することによってこれを実行できます。</span><span class="sxs-lookup"><span data-stu-id="1d437-179">For Z_EXTRACT_DATA_OO RFC, you can do so by performing the following tests to confirm that the RFC operates and is ready for use in your system.</span></span>  
  
##### <a name="to-test-the-installation-of-zextractdataoo"></a><span data-ttu-id="1d437-180">Z_EXTRACT_DATA_OO のインストールをテストするには</span><span class="sxs-lookup"><span data-stu-id="1d437-180">To test the installation of Z_EXTRACT_DATA_OO</span></span>  
  
1.  <span data-ttu-id="1d437-181">SAP GUI の承認管理ツールで SE37、関数モジュール Z_EXTRACT_DATA_OO を実行し、テスト モードでキーを押して、RFC を実行`F8`します。</span><span class="sxs-lookup"><span data-stu-id="1d437-181">In the SAP GUI authorization administration tools, execute SE37, function module Z_EXTRACT_DATA_OO, and then run the RFC in test mode by pressing `F8`.</span></span> <span data-ttu-id="1d437-182">次のように、パラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="1d437-182">Populate the parameters as follows.</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="1d437-183">IN_METADATA_ONLY</span><span class="sxs-lookup"><span data-stu-id="1d437-183">IN_METADATA_ONLY</span></span>||  
    |<span data-ttu-id="1d437-184">IN_METADATA_LANGUAGE</span><span class="sxs-lookup"><span data-stu-id="1d437-184">IN_METADATA_LANGUAGE</span></span>|<span data-ttu-id="1d437-185">EN</span><span class="sxs-lookup"><span data-stu-id="1d437-185">EN</span></span>|  
    |<span data-ttu-id="1d437-186">IN_FROM_TABLE</span><span class="sxs-lookup"><span data-stu-id="1d437-186">IN_FROM_TABLE</span></span>|<span data-ttu-id="1d437-187">T000</span><span class="sxs-lookup"><span data-stu-id="1d437-187">T000</span></span>|  
    |<span data-ttu-id="1d437-188">IN_OUTPUT_MODE</span><span class="sxs-lookup"><span data-stu-id="1d437-188">IN_OUTPUT_MODE</span></span>|<span data-ttu-id="1d437-189">S</span><span class="sxs-lookup"><span data-stu-id="1d437-189">S</span></span>|  
    |<span data-ttu-id="1d437-190">IN_OUTPUT_FILENAME</span><span class="sxs-lookup"><span data-stu-id="1d437-190">IN_OUTPUT_FILENAME</span></span>||  
    |<span data-ttu-id="1d437-191">IN_USE_FIELD_EXITS</span><span class="sxs-lookup"><span data-stu-id="1d437-191">IN_USE_FIELD_EXITS</span></span>|<span data-ttu-id="1d437-192">×</span><span class="sxs-lookup"><span data-stu-id="1d437-192">X</span></span>|  
    |<span data-ttu-id="1d437-193">IN_SET_ROWCOUNT</span><span class="sxs-lookup"><span data-stu-id="1d437-193">IN_SET_ROWCOUNT</span></span>|<span data-ttu-id="1d437-194">0</span><span class="sxs-lookup"><span data-stu-id="1d437-194">0</span></span>|  
    |<span data-ttu-id="1d437-195">IN_DELIMITER</span><span class="sxs-lookup"><span data-stu-id="1d437-195">IN_DELIMITER</span></span>||  
    |<span data-ttu-id="1d437-196">IN_PACKET_SIZE</span><span class="sxs-lookup"><span data-stu-id="1d437-196">IN_PACKET_SIZE</span></span>|<span data-ttu-id="1d437-197">50,000</span><span class="sxs-lookup"><span data-stu-id="1d437-197">50,000</span></span>|  
    |<span data-ttu-id="1d437-198">IN_MAX_WRITE_ATTEMPTS</span><span class="sxs-lookup"><span data-stu-id="1d437-198">IN_MAX_WRITE_ATTEMPTS</span></span>|<span data-ttu-id="1d437-199">4</span><span class="sxs-lookup"><span data-stu-id="1d437-199">4</span></span>|  
    |<span data-ttu-id="1d437-200">IN_RETRY_DELAY</span><span class="sxs-lookup"><span data-stu-id="1d437-200">IN_RETRY_DELAY</span></span>|<span data-ttu-id="1d437-201">30</span><span class="sxs-lookup"><span data-stu-id="1d437-201">30</span></span>|  
    |<span data-ttu-id="1d437-202">IN_SQL_DATES_ON</span><span class="sxs-lookup"><span data-stu-id="1d437-202">IN_SQL_DATES_ON</span></span>||  
  
2.  <span data-ttu-id="1d437-203">クリックして**Execute**またはキーを押します`F8`します。</span><span class="sxs-lookup"><span data-stu-id="1d437-203">Click **Execute** or press `F8`.</span></span>  
  
3.  <span data-ttu-id="1d437-204">結果ウィンドウで、次の手順を確認します。</span><span class="sxs-lookup"><span data-stu-id="1d437-204">In the results pane, check the following.</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="1d437-205">OUT_TABLEHEADER</span><span class="sxs-lookup"><span data-stu-id="1d437-205">OUT_TABLEHEADER</span></span>|<span data-ttu-id="1d437-206">\<T000 一般的なメタデータ\></span><span class="sxs-lookup"><span data-stu-id="1d437-206">\<T000 general metadata\></span></span>|  
    |<span data-ttu-id="1d437-207">OUT_TECHNICALSETTINGS</span><span class="sxs-lookup"><span data-stu-id="1d437-207">OUT_TECHNICALSETTINGS</span></span>|<span data-ttu-id="1d437-208">\<T000 テクニカル データベース レベルのメタデータ\></span><span class="sxs-lookup"><span data-stu-id="1d437-208">\<T000 technical database level metadata\></span></span>|  
    |<span data-ttu-id="1d437-209">OUT_RECORDLENGTH</span><span class="sxs-lookup"><span data-stu-id="1d437-209">OUT_RECORDLENGTH</span></span>|<span data-ttu-id="1d437-210">\<SAP バージョンによって異なります\></span><span class="sxs-lookup"><span data-stu-id="1d437-210">\<depends on SAP version\></span></span>|  
    |<span data-ttu-id="1d437-211">OUT_RECORDCOUNT</span><span class="sxs-lookup"><span data-stu-id="1d437-211">OUT_RECORDCOUNT</span></span>|<span data-ttu-id="1d437-212">\<SE16 T000 を使用しているシステムでクライアントの数を確認します。\></span><span class="sxs-lookup"><span data-stu-id="1d437-212">\<confirm the number of clients in your system with SE16 on T000\></span></span>|  
    |<span data-ttu-id="1d437-213">OUT_ZDATATABLE</span><span class="sxs-lookup"><span data-stu-id="1d437-213">OUT_ZDATATABLE</span></span>|<span data-ttu-id="1d437-214">\<T000 で SE 16 を使用してソース データでこの結果を確認します。\></span><span class="sxs-lookup"><span data-stu-id="1d437-214">\<confirm this result with the source data using SE 16 on T000\></span></span>|  
    |<span data-ttu-id="1d437-215">OUT_RETURN_TAB</span><span class="sxs-lookup"><span data-stu-id="1d437-215">OUT_RETURN_TAB</span></span>|<span data-ttu-id="1d437-216">S 001 成功</span><span class="sxs-lookup"><span data-stu-id="1d437-216">S 001 Success</span></span>|  
  
## <a name="remove-the-rfc-for-the-data-provider-for-sap"></a><span data-ttu-id="1d437-217">Data Provider for SAP の RFC を削除します。</span><span class="sxs-lookup"><span data-stu-id="1d437-217">Remove the RFC for the Data Provider for SAP</span></span>  
  
1.  <span data-ttu-id="1d437-218">SAP GUI オブジェクト ナビゲーター (SE80) ZMSBI 開発のクラスを使用してすべてのオブジェクトを検索します。</span><span class="sxs-lookup"><span data-stu-id="1d437-218">In the SAP GUI Object Navigator (SE80), find all the objects with the ZMSBI development class.</span></span>  
  
2.  <span data-ttu-id="1d437-219">Dictionary オブジェクトの次のフォルダーから ZMSBI 開発のクラスを使用してすべてのオブジェクトを削除します。</span><span class="sxs-lookup"><span data-stu-id="1d437-219">Delete all objects with the ZMSBI development class from the following Dictionary Objects folders:</span></span>  
  
    -   <span data-ttu-id="1d437-220">構造体</span><span class="sxs-lookup"><span data-stu-id="1d437-220">Structures</span></span>  
  
    -   <span data-ttu-id="1d437-221">関数グループ</span><span class="sxs-lookup"><span data-stu-id="1d437-221">Function Groups</span></span>  
  
    -   <span data-ttu-id="1d437-222">承認されたオブジェクト</span><span class="sxs-lookup"><span data-stu-id="1d437-222">Authorized Object</span></span>  
  
3.  <span data-ttu-id="1d437-223">トランスポートを生成し、RFC (開発、テスト、および実稼働システムに、たとえば) がインストールされている各システムを移行します。</span><span class="sxs-lookup"><span data-stu-id="1d437-223">Raise a transport, and migrate it through each system where you installed an RFC (development, test, and production systems, for example).</span></span>  
  
     <span data-ttu-id="1d437-224">詳細については、SAP 管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="1d437-224">For further assistance, contact your SAP Basis Administrator.</span></span>  
     
## <a name="next"></a><span data-ttu-id="1d437-225">Next</span><span class="sxs-lookup"><span data-stu-id="1d437-225">Next</span></span>
[<span data-ttu-id="1d437-226">BizTalk Adapter for mySAP Business Suite について</span><span class="sxs-lookup"><span data-stu-id="1d437-226">Understand BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)  
[<span data-ttu-id="1d437-227">SAP アダプター チュートリアル</span><span class="sxs-lookup"><span data-stu-id="1d437-227">SAP Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)