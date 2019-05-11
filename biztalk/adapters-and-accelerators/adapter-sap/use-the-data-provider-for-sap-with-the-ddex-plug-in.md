---
title: DDEX プラグインでの SAP のため、データ プロバイダーを使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DDEX plug-in
- DDEX plug-in, Data Provider for SAP
- Data Provider for SAP, using with DDEX plug-in
ms.assetid: b16c8634-172a-4630-87ed-2073a75afdec
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 552d77518e7e7481efa2ee5eb5dda6908662429c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372069"
---
# <a name="use-the-data-provider-for-sap-with-the-ddex-plug-in"></a><span data-ttu-id="c1634-102">DDEX プラグインで SAP 用データ プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="c1634-102">Use the Data Provider for SAP with the DDEX Plug-in</span></span>
<span data-ttu-id="c1634-103">インストールした場合、[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]と共に、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] 、インストール、セットアップ プログラムによって、 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] DDEX プラグイン。</span><span class="sxs-lookup"><span data-stu-id="c1634-103">If you chose to install the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] along with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation, the setup program installs a [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] DDEX plug-in.</span></span> <span data-ttu-id="c1634-104">使用して、SAP オブジェクトを参照するこのプラグインを使用することができます[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c1634-104">You can use this plug-in to browse SAP objects using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="c1634-105">このセクションでは、DDEX プラグインの使用に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c1634-105">This section provides information about using the DDEX plug-in.</span></span>  
  
 <span data-ttu-id="c1634-106">プラグインを使用して、SAP システムからテーブルを追加、SAP システムとの接続を確立し、SAP システムから関数モジュールを追加します。</span><span class="sxs-lookup"><span data-stu-id="c1634-106">You can use the plug-in to establish connectivity with the SAP system, add tables from the SAP system, and add function modules from the SAP system.</span></span> <span data-ttu-id="c1634-107">テーブルと Visual Studio プラグインを使用して、関数モジュールを追加した後は、新しく追加されたテーブルと関数モジュールが SAPDiscoveredObjects.xml ファイルに反映されます。</span><span class="sxs-lookup"><span data-stu-id="c1634-107">After you have added the tables and function modules using the Visual Studio plug-in, the newly added tables and function modules are reflected in the SAPDiscoveredObjects.xml file.</span></span> <span data-ttu-id="c1634-108">このファイルの詳細については、次を参照してください。[について SAPDiscoveredObjects.xml ファイル sap](../../adapters-and-accelerators/adapter-sap/about-the-sapdiscoveredobjects-xml-file-in-sap.md)します。</span><span class="sxs-lookup"><span data-stu-id="c1634-108">For more information about this file, see [About the SAPDiscoveredObjects.xml File in SAP](../../adapters-and-accelerators/adapter-sap/about-the-sapdiscoveredobjects-xml-file-in-sap.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c1634-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="c1634-109">Prerequisites</span></span>  
 <span data-ttu-id="c1634-110">インストールするかどうかを確認、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]と共に、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="c1634-110">Make sure you chose to install the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] along with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation.</span></span>  
  
### <a name="to-connect-to-an-sap-system-using-the-ddex-plug-in"></a><span data-ttu-id="c1634-111">DDEX プラグインを使用して SAP システムに接続するには</span><span class="sxs-lookup"><span data-stu-id="c1634-111">To connect to an SAP system using the DDEX plug-in</span></span>  
  
1. <span data-ttu-id="c1634-112">Microsoft の開始[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c1634-112">Start Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
2. <span data-ttu-id="c1634-113">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の**ビュー** メニューのをクリックして**サーバー エクスプ ローラー**です。</span><span class="sxs-lookup"><span data-stu-id="c1634-113">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **View** menu, click **Server Explorer**.</span></span>  
  
3. <span data-ttu-id="c1634-114">**サーバー エクスプ ローラー**を右クリックして**データ接続**、選び**接続の追加**します。</span><span class="sxs-lookup"><span data-stu-id="c1634-114">In the **Server Explorer**, right-click **Data Connections**, and select **Add Connection**.</span></span>  
  
4. <span data-ttu-id="c1634-115">**データ ソースの変更** ダイアログ ボックスから、**データ ソース**ボックスで、 **\<他\>** します。</span><span class="sxs-lookup"><span data-stu-id="c1634-115">In the **Change Data Source** dialog box, from the **Data source** box, select **\<other\>**.</span></span>  
  
5. <span data-ttu-id="c1634-116">**データ プロバイダー**ドロップダウン リストで、 **mySAP Business Suite の .NET Framework Data Provider**  をクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="c1634-116">From the **Data provider** drop-down list, select **.NET Framework Data Provider for mySAP Business Suite** and click **OK**.</span></span> <span data-ttu-id="c1634-117">**接続の追加** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1634-117">The **Add Connection** dialog box opens.</span></span>  
  
6. <span data-ttu-id="c1634-118">**接続の追加** ダイアログ ボックスには、SAP システムへの接続に別の接続パラメーターが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1634-118">The **Add Connection** dialog box lists the different connection parameters to connect to an SAP system.</span></span> <span data-ttu-id="c1634-119">SAP システムを使用して接続するための一般的な接続文字列、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]が必要です。</span><span class="sxs-lookup"><span data-stu-id="c1634-119">A typical connection string to connect to an SAP system using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requires:</span></span>  
  
   - <span data-ttu-id="c1634-120">接続の種類の接続パラメーター。</span><span class="sxs-lookup"><span data-stu-id="c1634-120">The connection parameters for a connection type.</span></span> <span data-ttu-id="c1634-121">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] A、B、および D の接続の種類をサポートしていますSAP システムへの接続には、いずれかの接続パラメーターを指定する必要があります*1 つ*のこれらの接続の種類。</span><span class="sxs-lookup"><span data-stu-id="c1634-121">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] supports connection types A, B, and D. To connect to an SAP system you must provide connection parameters for any *one* of these connection types.</span></span> <span data-ttu-id="c1634-122">たとえば、A の接続の種類、アプリケーション サーバーのホストとシステムの数の名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1634-122">For example, for connection type A, you must provide the name of the application server host and the system number.</span></span>  
  
   - <span data-ttu-id="c1634-123">ユーザー名とパスワードなどの SAP システムに接続するログイン情報。</span><span class="sxs-lookup"><span data-stu-id="c1634-123">The login information to connect to an SAP system such as username and password.</span></span>  
  
     <span data-ttu-id="c1634-124">SAP システムを使用して接続する接続文字列の詳細については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[SAP 接続文字列のデータ プロバイダーの種類について](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)します。</span><span class="sxs-lookup"><span data-stu-id="c1634-124">For more information about the connection string to connect to an SAP system using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Read about Data Provider types for the SAP Connection String](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span></span>  
  
     <span data-ttu-id="c1634-125">**接続の追加** ダイアログ ボックスで指定します。</span><span class="sxs-lookup"><span data-stu-id="c1634-125">In the **Add Connection** dialog box, specify:</span></span>  
  
   - <span data-ttu-id="c1634-126">任意の 1 つの接続の接続パラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="c1634-126">The connection parameters for any one connection type.</span></span>  
  
   - <span data-ttu-id="c1634-127">SAP システムへの接続にログイン情報。</span><span class="sxs-lookup"><span data-stu-id="c1634-127">The login information to connect to an SAP system.</span></span>  
  
   - <span data-ttu-id="c1634-128">SAP GUI のデバッグを有効にするかどうか。</span><span class="sxs-lookup"><span data-stu-id="c1634-128">Whether you want to enable SAP GUI debugging.</span></span>  
  
   - <span data-ttu-id="c1634-129">RFC SDK トレースを使用するかどうか。</span><span class="sxs-lookup"><span data-stu-id="c1634-129">Whether you want to use RFC SDK tracing.</span></span>  
  
     <span data-ttu-id="c1634-130">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1634-130">Click **OK**.</span></span> <span data-ttu-id="c1634-131">新しい接続ノードが作成された、**データ接続**を前の手順で指定したサーバー名のノード。</span><span class="sxs-lookup"><span data-stu-id="c1634-131">A new connection node is created under the **Data Connections** node with the server name you specified in the previous step.</span></span>  
  
7. <span data-ttu-id="c1634-132">表示する新しい接続ノードを展開し、**テーブル**と**関数モジュール**ノード。</span><span class="sxs-lookup"><span data-stu-id="c1634-132">Expand the new connection node to view the **Tables** and **Function Modules** nodes.</span></span>  
  
    <span data-ttu-id="c1634-133">次の図は、接続が確立された後に、サーバー エクスプ ローラーを示します。</span><span class="sxs-lookup"><span data-stu-id="c1634-133">The following figure shows the Server Explorer after the connection is established.</span></span>  
  
    <span data-ttu-id="c1634-134">![DDEX プラグイン&#45;で SAP ADO.NET プロバイダーの](../../adapters-and-accelerators/adapter-sap/media/158afc11-9c90-4333-bc62-5901f8d0c794.gif "158afc11-9c90-4333-bc62-5901f8d0c794")</span><span class="sxs-lookup"><span data-stu-id="c1634-134">![DDEX plug&#45;in for SAP ADO.NET Provider](../../adapters-and-accelerators/adapter-sap/media/158afc11-9c90-4333-bc62-5901f8d0c794.gif "158afc11-9c90-4333-bc62-5901f8d0c794")</span></span>  
  
### <a name="to-add-tables-from-an-sap-system-using-the-ddex-plug-in"></a><span data-ttu-id="c1634-135">DDEX プラグインを使用して SAP システムからテーブルを追加するには</span><span class="sxs-lookup"><span data-stu-id="c1634-135">To add tables from an SAP system using the DDEX plug-in</span></span>  
  
1. <span data-ttu-id="c1634-136">**サーバー エクスプ ローラー**を右クリックし、**テーブル**ノードをクリックします**検索し、テーブルの追加**します。</span><span class="sxs-lookup"><span data-stu-id="c1634-136">In the **Server Explorer**, right-click the **Tables** node and click **Search and Add Tables**.</span></span>  
  
2. <span data-ttu-id="c1634-137">**検索テーブル名**テキスト ボックスで、SAP システム内のテーブルを検索し、をクリックする検索文字列を指定します。**検索**します。</span><span class="sxs-lookup"><span data-stu-id="c1634-137">In the **Search table name** text box, specify a search string to search tables in the SAP system, and click **Search**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="c1634-138">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]テーブルを検索するためのアスタリスク (\*) ワイルドカード文字のみの使用をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c1634-138">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] supports the use of only the asterisk (\*) wildcard character for searching tables.</span></span>  
  
3. <span data-ttu-id="c1634-139">**検索結果**ボックスに検索条件を満たすテーブル名が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1634-139">The **Search results** box lists the table names that satisfy the search criteria.</span></span>  
  
    <span data-ttu-id="c1634-140">![DDEX プラグイン&#45;検索および追加のテーブル名 ダイアログ ボックスで](../../adapters-and-accelerators/adapter-sap/media/737fc9c3-5258-4693-a2f3-5b5b8d2483e9.gif "737fc9c3-5258-4693-a2f3-5b5b8d2483e9")</span><span class="sxs-lookup"><span data-stu-id="c1634-140">![DDEX plug&#45;in Search and Add Tables name dialog box](../../adapters-and-accelerators/adapter-sap/media/737fc9c3-5258-4693-a2f3-5b5b8d2483e9.gif "737fc9c3-5258-4693-a2f3-5b5b8d2483e9")</span></span>  
  
4. <span data-ttu-id="c1634-141">追加し、をクリックするテーブルに対応するチェック ボックスをオン**追加**します。</span><span class="sxs-lookup"><span data-stu-id="c1634-141">Select the check box corresponding to the tables you want to add and click **Add**.</span></span> <span data-ttu-id="c1634-142">すべてのテーブルを選択する をクリックして**すべて選択**します。</span><span class="sxs-lookup"><span data-stu-id="c1634-142">To select all the tables, click **Select All**.</span></span> <span data-ttu-id="c1634-143">すべての選択を解除するには、次のようにクリックします。**すべてクリア**します。</span><span class="sxs-lookup"><span data-stu-id="c1634-143">To clear all the selections, click **Clear All**.</span></span>  
  
5. <span data-ttu-id="c1634-144">ダイアログ ボックスは、更新した後に追加されたテーブルを表示がされることを通知、**テーブル**ノード。</span><span class="sxs-lookup"><span data-stu-id="c1634-144">A dialog box informs you that the added tables would be visible after you refresh the **Tables** node.</span></span> <span data-ttu-id="c1634-145">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1634-145">Click **OK**.</span></span>  
  
6. <span data-ttu-id="c1634-146">右クリックし、**テーブル**ノード**更新**します。</span><span class="sxs-lookup"><span data-stu-id="c1634-146">Right-click the **Tables** node and select **Refresh**.</span></span> <span data-ttu-id="c1634-147">選択したテーブルを下に表示されます、**テーブル**ノード。</span><span class="sxs-lookup"><span data-stu-id="c1634-147">The selected tables appear under the **Tables** node.</span></span> <span data-ttu-id="c1634-148">テーブルのプロパティを表示するテーブル名をクリックして、**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="c1634-148">Click a table name to see the table properties in the **Properties** pane.</span></span>  
  
7. <span data-ttu-id="c1634-149">テーブルのフィールドを表示するテーブル名を展開します。</span><span class="sxs-lookup"><span data-stu-id="c1634-149">Expand a table name to see the fields for the table.</span></span> <span data-ttu-id="c1634-150">フィールド プロパティを表示するフィールド名をクリックして、**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="c1634-150">Click a field name to see the field properties in the **Properties** pane.</span></span>  
  
### <a name="to-add-rfcs-from-an-sap-system-using-the-ddex-plug-in"></a><span data-ttu-id="c1634-151">DDEX プラグインを使用して SAP システムから Rfc を追加するには</span><span class="sxs-lookup"><span data-stu-id="c1634-151">To add RFCs from an SAP system using the DDEX plug-in</span></span>  
  
1. <span data-ttu-id="c1634-152">**サーバー エクスプ ローラー**を右クリックし、**関数モジュール**ノードをクリックします**関数モジュールの追加の検索および**します。</span><span class="sxs-lookup"><span data-stu-id="c1634-152">In the **Server Explorer**, right-click the **Function Modules** node and click **Search and Add Function Modules**.</span></span>  
  
2. <span data-ttu-id="c1634-153">**検索関数モジュール**テキスト ボックスで、SAP システムで関数モジュールを検索し、をクリックする検索文字列を指定します。**検索**します。</span><span class="sxs-lookup"><span data-stu-id="c1634-153">In the **Search function module** text box, specify a search string to search function modules in the SAP system, and click **Search**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="c1634-154">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]機能モジュールを検索するためのアスタリスク (\*) ワイルドカード文字のみの使用をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c1634-154">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] supports the use of only the asterisk (\*) wildcard character for searching functional modules.</span></span>  
  
3. <span data-ttu-id="c1634-155">**検索結果**ボックスに検索条件を満たす関数モジュールが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1634-155">The **Search results** box lists the function modules that satisfy the search criteria.</span></span>  
  
    <span data-ttu-id="c1634-156">![DDEX プラグイン&#45;検索とモジュールの追加 ダイアログ ボックスで](../../adapters-and-accelerators/adapter-sap/media/8c7f9081-80aa-4bfe-8f06-2c751758ddd0.gif "8c7f9081-80aa-4bfe-8f06-2c751758ddd0")</span><span class="sxs-lookup"><span data-stu-id="c1634-156">![DDEX plug&#45;in Search and Add Modules dialog box](../../adapters-and-accelerators/adapter-sap/media/8c7f9081-80aa-4bfe-8f06-2c751758ddd0.gif "8c7f9081-80aa-4bfe-8f06-2c751758ddd0")</span></span>  
  
4. <span data-ttu-id="c1634-157">追加し、をクリックする関数モジュールに対応するチェック ボックスをオン**追加**します。</span><span class="sxs-lookup"><span data-stu-id="c1634-157">Select the check box corresponding to the function modules you want to add and click **Add**.</span></span> <span data-ttu-id="c1634-158">すべてのモジュールを選択するには、次のようにクリックします。**すべて選択**します。</span><span class="sxs-lookup"><span data-stu-id="c1634-158">To select all the modules, click **Select All**.</span></span> <span data-ttu-id="c1634-159">すべての選択を解除するには、次のようにクリックします。**すべてクリア**します。</span><span class="sxs-lookup"><span data-stu-id="c1634-159">To clear all the selections, click **Clear All**.</span></span>  
  
5. <span data-ttu-id="c1634-160">ダイアログ ボックスは、更新した後に追加された関数モジュールを表示がされることを通知、**関数モジュール**ノード。</span><span class="sxs-lookup"><span data-stu-id="c1634-160">A dialog box informs you that the added function modules would be visible after you refresh the **Function Modules** node.</span></span> <span data-ttu-id="c1634-161">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1634-161">Click **OK**.</span></span>  
  
6. <span data-ttu-id="c1634-162">右クリックし、**関数モジュール**ノード**更新**します。</span><span class="sxs-lookup"><span data-stu-id="c1634-162">Right-click the **Function Modules** node and select **Refresh**.</span></span> <span data-ttu-id="c1634-163">選択した関数モジュールは、下に表示されます、**関数モジュール**ノード。</span><span class="sxs-lookup"><span data-stu-id="c1634-163">The selected function modules appear under the **Function Modules** node.</span></span> <span data-ttu-id="c1634-164">プロパティを表示する関数モジュール名をクリックして、**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="c1634-164">Click a function module name to see the properties in the **Properties** pane.</span></span>  
  
7. <span data-ttu-id="c1634-165">インポート、エクスポート、変更、およびテーブル パラメーターのノードを表示する関数モジュール名を展開します。</span><span class="sxs-lookup"><span data-stu-id="c1634-165">Expand a function module name to see nodes for import, export, changing, and table parameters.</span></span>  
  
8. <span data-ttu-id="c1634-166">展開、**インポート**関数モジュールのインポートのパラメーターを一覧表示するノード。</span><span class="sxs-lookup"><span data-stu-id="c1634-166">Expand the **Import** node to list the import parameters for the function module.</span></span> <span data-ttu-id="c1634-167">同様に、展開、**エクスポート**と**テーブル**関数モジュールのパラメーターをエクスポートし、テーブルの一覧を表示するノード。</span><span class="sxs-lookup"><span data-stu-id="c1634-167">Similarly, expand the **Export** and **Tables** nodes to see the list of export and table parameters for the function module.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1634-168">参照</span><span class="sxs-lookup"><span data-stu-id="c1634-168">See Also</span></span>  
 [<span data-ttu-id="c1634-169">.NET Framework Data Provider for mySAP Business Suite の使用</span><span class="sxs-lookup"><span data-stu-id="c1634-169">Use the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)