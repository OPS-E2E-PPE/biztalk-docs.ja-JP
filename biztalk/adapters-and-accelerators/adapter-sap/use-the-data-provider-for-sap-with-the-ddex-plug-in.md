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
# <a name="use-the-data-provider-for-sap-with-the-ddex-plug-in"></a>DDEX プラグインで SAP 用データ プロバイダーを使用します。
インストールした場合、[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]と共に、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] 、インストール、セットアップ プログラムによって、 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] DDEX プラグイン。 使用して、SAP オブジェクトを参照するこのプラグインを使用することができます[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。 このセクションでは、DDEX プラグインの使用に関する情報を提供します。  
  
 プラグインを使用して、SAP システムからテーブルを追加、SAP システムとの接続を確立し、SAP システムから関数モジュールを追加します。 テーブルと Visual Studio プラグインを使用して、関数モジュールを追加した後は、新しく追加されたテーブルと関数モジュールが SAPDiscoveredObjects.xml ファイルに反映されます。 このファイルの詳細については、次を参照してください。[について SAPDiscoveredObjects.xml ファイル sap](../../adapters-and-accelerators/adapter-sap/about-the-sapdiscoveredobjects-xml-file-in-sap.md)します。  
  
## <a name="prerequisites"></a>前提条件  
 インストールするかどうかを確認、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]と共に、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]インストールします。  
  
### <a name="to-connect-to-an-sap-system-using-the-ddex-plug-in"></a>DDEX プラグインを使用して SAP システムに接続するには  
  
1. Microsoft の開始[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。  
  
2. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の**ビュー** メニューのをクリックして**サーバー エクスプ ローラー**です。  
  
3. **サーバー エクスプ ローラー**を右クリックして**データ接続**、選び**接続の追加**します。  
  
4. **データ ソースの変更** ダイアログ ボックスから、**データ ソース**ボックスで、 **\<他\>** します。  
  
5. **データ プロバイダー**ドロップダウン リストで、 **mySAP Business Suite の .NET Framework Data Provider**  をクリック**OK**します。 **接続の追加** ダイアログ ボックスが表示されます。  
  
6. **接続の追加** ダイアログ ボックスには、SAP システムへの接続に別の接続パラメーターが一覧表示されます。 SAP システムを使用して接続するための一般的な接続文字列、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]が必要です。  
  
   - 接続の種類の接続パラメーター。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] A、B、および D の接続の種類をサポートしていますSAP システムへの接続には、いずれかの接続パラメーターを指定する必要があります*1 つ*のこれらの接続の種類。 たとえば、A の接続の種類、アプリケーション サーバーのホストとシステムの数の名前を指定する必要があります。  
  
   - ユーザー名とパスワードなどの SAP システムに接続するログイン情報。  
  
     SAP システムを使用して接続する接続文字列の詳細については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[SAP 接続文字列のデータ プロバイダーの種類について](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)します。  
  
     **接続の追加** ダイアログ ボックスで指定します。  
  
   - 任意の 1 つの接続の接続パラメーターを入力します。  
  
   - SAP システムへの接続にログイン情報。  
  
   - SAP GUI のデバッグを有効にするかどうか。  
  
   - RFC SDK トレースを使用するかどうか。  
  
     **[OK]** をクリックします。 新しい接続ノードが作成された、**データ接続**を前の手順で指定したサーバー名のノード。  
  
7. 表示する新しい接続ノードを展開し、**テーブル**と**関数モジュール**ノード。  
  
    次の図は、接続が確立された後に、サーバー エクスプ ローラーを示します。  
  
    ![DDEX プラグイン&#45;で SAP ADO.NET プロバイダーの](../../adapters-and-accelerators/adapter-sap/media/158afc11-9c90-4333-bc62-5901f8d0c794.gif "158afc11-9c90-4333-bc62-5901f8d0c794")  
  
### <a name="to-add-tables-from-an-sap-system-using-the-ddex-plug-in"></a>DDEX プラグインを使用して SAP システムからテーブルを追加するには  
  
1. **サーバー エクスプ ローラー**を右クリックし、**テーブル**ノードをクリックします**検索し、テーブルの追加**します。  
  
2. **検索テーブル名**テキスト ボックスで、SAP システム内のテーブルを検索し、をクリックする検索文字列を指定します。**検索**します。  
  
   > [!NOTE]
   >  [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]テーブルを検索するためのアスタリスク (*) ワイルドカード文字のみの使用をサポートしています。  
  
3. **検索結果**ボックスに検索条件を満たすテーブル名が一覧表示されます。  
  
    ![DDEX プラグイン&#45;検索および追加のテーブル名 ダイアログ ボックスで](../../adapters-and-accelerators/adapter-sap/media/737fc9c3-5258-4693-a2f3-5b5b8d2483e9.gif "737fc9c3-5258-4693-a2f3-5b5b8d2483e9")  
  
4. 追加し、をクリックするテーブルに対応するチェック ボックスをオン**追加**します。 すべてのテーブルを選択する をクリックして**すべて選択**します。 すべての選択を解除するには、次のようにクリックします。**すべてクリア**します。  
  
5. ダイアログ ボックスは、更新した後に追加されたテーブルを表示がされることを通知、**テーブル**ノード。 **[OK]** をクリックします。  
  
6. 右クリックし、**テーブル**ノード**更新**します。 選択したテーブルを下に表示されます、**テーブル**ノード。 テーブルのプロパティを表示するテーブル名をクリックして、**プロパティ**ウィンドウ。  
  
7. テーブルのフィールドを表示するテーブル名を展開します。 フィールド プロパティを表示するフィールド名をクリックして、**プロパティ**ウィンドウ。  
  
### <a name="to-add-rfcs-from-an-sap-system-using-the-ddex-plug-in"></a>DDEX プラグインを使用して SAP システムから Rfc を追加するには  
  
1. **サーバー エクスプ ローラー**を右クリックし、**関数モジュール**ノードをクリックします**関数モジュールの追加の検索および**します。  
  
2. **検索関数モジュール**テキスト ボックスで、SAP システムで関数モジュールを検索し、をクリックする検索文字列を指定します。**検索**します。  
  
   > [!NOTE]
   >  [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]機能モジュールを検索するためのアスタリスク (*) ワイルドカード文字のみの使用をサポートしています。  
  
3. **検索結果**ボックスに検索条件を満たす関数モジュールが一覧表示されます。  
  
    ![DDEX プラグイン&#45;検索とモジュールの追加 ダイアログ ボックスで](../../adapters-and-accelerators/adapter-sap/media/8c7f9081-80aa-4bfe-8f06-2c751758ddd0.gif "8c7f9081-80aa-4bfe-8f06-2c751758ddd0")  
  
4. 追加し、をクリックする関数モジュールに対応するチェック ボックスをオン**追加**します。 すべてのモジュールを選択するには、次のようにクリックします。**すべて選択**します。 すべての選択を解除するには、次のようにクリックします。**すべてクリア**します。  
  
5. ダイアログ ボックスは、更新した後に追加された関数モジュールを表示がされることを通知、**関数モジュール**ノード。 **[OK]** をクリックします。  
  
6. 右クリックし、**関数モジュール**ノード**更新**します。 選択した関数モジュールは、下に表示されます、**関数モジュール**ノード。 プロパティを表示する関数モジュール名をクリックして、**プロパティ**ウィンドウ。  
  
7. インポート、エクスポート、変更、およびテーブル パラメーターのノードを表示する関数モジュール名を展開します。  
  
8. 展開、**インポート**関数モジュールのインポートのパラメーターを一覧表示するノード。 同様に、展開、**エクスポート**と**テーブル**関数モジュールのパラメーターをエクスポートし、テーブルの一覧を表示するノード。  
  
## <a name="see-also"></a>参照  
 [.NET Framework Data Provider for mySAP Business Suite の使用](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)