---
title: DDEX プラグインと SAP 用データ プロバイダーを使用して |Microsoft ドキュメント
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
ms.openlocfilehash: a2a1dd348b6d897e147d6add49499e9716a67aeb
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "25963464"
---
# <a name="use-the-data-provider-for-sap-with-the-ddex-plug-in"></a>DDEX プラグインと SAP 用データ プロバイダーを使用します。
インストールする場合、[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]と共に、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]インストール、セットアップ プログラムをインストール、 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] DDEX プラグインします。 使用して、SAP オブジェクトを参照するこのプラグインを使用することができます[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。 このセクションでは、DDEX プラグインの使用に関する情報を提供します。  
  
 プラグインを使用して、SAP システムからテーブルを追加、SAP システムとの接続を確立し、SAP システムから関数モジュールを追加できます。 テーブルと Visual Studio プラグインを使用して関数モジュールを追加した後、新しく追加されたテーブルと関数モジュールが SAPDiscoveredObjects.xml ファイルに反映されます。 このファイルの詳細については、次を参照してください。[に関する「SAPDiscoveredObjects.xml ファイルの SAP の](../../adapters-and-accelerators/adapter-sap/about-the-sapdiscoveredobjects-xml-file-in-sap.md)します。  
  
## <a name="prerequisites"></a>前提条件  
 インストールするかどうかを確認、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]と共に、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]インストールします。  
  
### <a name="to-connect-to-an-sap-system-using-the-ddex-plug-in"></a>DDEX プラグインを使用して SAP システムに接続するには  
  
1.  Microsoft の開始[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。  
  
2.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の**ビュー** メニューのをクリックして**サーバー エクスプ ローラー**です。  
  
3.  **サーバー エクスプ ローラー**を右クリックして**データ接続**を選択して**接続の追加**です。  
  
4.  **データ ソースの変更** ダイアログ ボックスから、**データ ソース**ボックスで、 **\<他\>** です。  
  
5.  **データ プロバイダー**ドロップダウン リストで、 **.NET Framework Data Provider 用 mySAP Business Suite**  をクリック**OK**です。 **接続の追加** ダイアログ ボックスが表示されます。  
  
6.  **接続の追加** ダイアログ ボックスには、SAP システムへの接続に別の接続パラメーターが一覧表示されます。 使用して SAP システムへの接続に一般的な接続文字列、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]が必要です。  
  
    -   接続の接続パラメーターを入力します。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] A、B、および D の接続の種類をサポートしていますSAP システムへの接続には、いずれかの接続パラメーターを指定する必要があります*1*種類の接続をします。 たとえば、接続の種類、システム数と、アプリケーション サーバーのホストの名前を指定する必要があります。  
  
    -   ユーザー名やパスワードなど、SAP システムへの接続にログイン情報。  
  
     使用して SAP システムへの接続への接続文字列の詳細については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[SAP 接続文字列のデータ プロバイダーの種類の説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)です。  
  
     **接続の追加** ダイアログ ボックスで指定します。  
  
    -   任意の 1 つの接続の接続パラメーターを入力します。  
  
    -   SAP システムへの接続にログイン情報。  
  
    -   SAP GUI のデバッグを有効にするかどうか。  
  
    -   RFC SDK トレースを使用するかどうか。  
  
     **[OK]** をクリックします。 新しい接続ノードを作成、**データ接続**前の手順で指定したサーバー名を持つノード。  
  
7.  ノードを展開して、新しい接続を表示、**テーブル**と**関数モジュール**ノード。  
  
     次の図は、接続が確立された後に、サーバー エクスプ ローラーを示します。  
  
     ![DDEX プラグイン&#45;で SAP ADO.NET プロバイダーの](../../adapters-and-accelerators/adapter-sap/media/158afc11-9c90-4333-bc62-5901f8d0c794.gif "158afc11-9c90-4333-bc62-5901f8d0c794")  
  
### <a name="to-add-tables-from-an-sap-system-using-the-ddex-plug-in"></a>DDEX プラグインを使用して SAP システムからテーブルを追加するには  
  
1.  **サーバー エクスプ ローラー**を右クリックし、**テーブル**ノードをクリック**検索し、テーブルの追加**です。  
  
2.  **検索テーブル名**テキスト ボックスで、SAP システム内のテーブルを検索し、クリックしての検索文字列を指定**検索**です。  
  
    > [!NOTE]
    >  [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]テーブルの検索のアスタリスク (*) ワイルドカード文字のみの使用をサポートします。  
  
3.  **検索結果**ボックスに検索条件を満たすテーブル名が一覧表示されます。  
  
     ![DDEX プラグイン&#45;検索および追加のテーブル名 ダイアログ ボックスで](../../adapters-and-accelerators/adapter-sap/media/737fc9c3-5258-4693-a2f3-5b5b8d2483e9.gif "737fc9c3-5258-4693-a2f3-5b5b8d2483e9")  
  
4.  追加し、をクリックするテーブルに対応するチェック ボックスをオンに**追加**です。 すべてのテーブルを選択するには、をクリックして**すべて選択**です。 すべての選択をクリアする をクリックして**すべてクリア**です。  
  
5.  ダイアログ ボックスで通知する追加されたテーブルが表示される更新したら、**テーブル**ノード。 **[OK]** をクリックします。  
  
6.  右クリックし、**テーブル**ノード**更新**です。 選択したテーブルが表示される、**テーブル**ノード。 テーブルのプロパティを表示するテーブル名をクリックして、**プロパティ**ウィンドウです。  
  
7.  テーブルのフィールドを表示するテーブル名を展開します。 フィールドのプロパティを表示するフィールド名をクリックして、**プロパティ**ウィンドウです。  
  
### <a name="to-add-rfcs-from-an-sap-system-using-the-ddex-plug-in"></a>DDEX プラグインを使用して SAP システムからの Rfc を追加するには  
  
1.  **サーバー エクスプ ローラー**を右クリックし、**関数モジュール**ノードとクリック**関数モジュールの追加の検索および**です。  
  
2.  **検索関数モジュール**テキスト ボックスに、システムでは、SAP、関数モジュールを検索し、クリックする検索文字列を指定**検索**です。  
  
    > [!NOTE]
    >  [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]機能モジュールを検索するためのアスタリスク (*) ワイルドカード文字のみの使用をサポートしています。  
  
3.  **検索結果**ボックスに検索条件に一致する関数モジュールが一覧表示されます。  
  
     ![DDEX プラグイン&#45;検索とモジュールの追加 ダイアログ ボックスで](../../adapters-and-accelerators/adapter-sap/media/8c7f9081-80aa-4bfe-8f06-2c751758ddd0.gif "8c7f9081-80aa-4bfe-8f06-2c751758ddd0")  
  
4.  追加し、をクリックする関数モジュールに対応するチェック ボックスをオンに**追加**です。 すべてのモジュールを選択するには、をクリックして**すべて選択**です。 すべての選択をクリアする をクリックして**すべてクリア**です。  
  
5.  ダイアログ ボックスで通知する関数が追加されたモジュールが表示されるを更新したら、**関数モジュール**ノード。 **[OK]** をクリックします。  
  
6.  右クリックし、**関数モジュール**ノード**更新**です。 選択した関数モジュールが表示されます、**関数モジュール**ノード。 プロパティを表示する関数モジュール名をクリックして、**プロパティ**ウィンドウです。  
  
7.  インポート、エクスポート、変更、およびテーブルのパラメーターのノードを表示する関数モジュール名を展開します。  
  
8.  展開して、**インポート**関数モジュールのインポートのパラメーターを一覧表示するノードです。 同様に、展開、**エクスポート**と**テーブル**関数モジュールのエクスポートとテーブルのパラメーターの一覧を表示するノードです。  
  
## <a name="see-also"></a>参照  
 [.NET Framework Data Provider for mySAP Business Suite の使用](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)