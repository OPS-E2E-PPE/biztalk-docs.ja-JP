---
title: "SAP 用データ プロバイダーのカスタム Rfc のインストール |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- installation, custom RFCs for the Data Provider for SAP
- installing, custom RFCs for the Data Provider for SAP
- installing custom RFCs, how to
ms.assetid: 7a99db70-fa5a-4c04-9dc7-b71613d4364e
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0aff501e5bf59d6ae22d9ad2a00e0e5ff5ad4605
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="install-custom-rfcs-for-the-data-provider-for-sap"></a>SAP 用データ プロバイダーのカスタム Rfc をインストールします。
MySAP Business Suite の SAP システムにアクセスする .NET Framework データ プロバイダーを使用する場合は、カスタムの Rfc をインストールします。

[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]カスタム Rfc に SAP システムに対して何らかの操作を実行する必要があります。
  
-   SELECT の操作を実行、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] Z_EXTRACT_DATA_OO RFC が必要です。  
  
-   EXECQUERY 操作の実行、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] Z_EXECUTE_SAP_QUERY RFC が必要です。  
  
SAP システムでこれらの操作を実行するには、SAP システムでこれらのカスタム Rfc をインストールする必要があります。 インストールする場合、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]と共に、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]、セットアップ プログラムによってコピーの RFC トランスポート、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]圧縮ファイル (customRFC.zip) システムでアダプターをインストールするとします。 Zip ファイルが通常にインストールされている*\<インストール ドライブ\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Microsoft .NET Framework Data Provider 用 mySAP Business Suite*です。 
  
 Zip ファイルを抽出するには、後に 4 つのデータ ファイルが表示されます、2 つの次の名前付けパターン K9 * です。BI1 (たとえば、K900534 に似ています。BI1)、およびその他の 2 つ次のパターン R9\*です。BI1 (たとえば、R900534 に似ています。BI1)。  
  

  
1.  SAP アプリケーション サーバーに、アダプターを実行しているコンピューターから抽出したファイルをコピーします。  
  
    1.  開発システムの SAP アプリケーション サーバーに SAP R/3 システム管理者としてログインします。  
  
    2.  名前付けパターン K9 * を持つ 2 つのトランスポート ファイルをコピーします。SAP アプリケーション サーバーで次のディレクトリに、アダプターを実行しているコンピューター上のインストール ディレクトリから BI1:  
  
         `<drive>:\usr\sap\trans\cofiles`  
  
    3.  名前付けパターン R9 * を持つ 2 つのトランスポート ファイルをコピーします。SAP アプリケーション サーバーで次のディレクトリに、アダプターを実行しているコンピューター上のインストール ディレクトリから BI1:  
  
         `<drive>:\usr\sap\trans\data`  
  
2.  SAP アプリケーション サーバー上のトランスポート バッファーにトランスポートを読み込みます。  
  
    1.  コマンド プロンプトでは、SAP アプリケーション サーバーで、トランスポートのプログラム ディレクトリに移動します。  
  
         `<drive>:\usr\sap\trans\bin`  
  
    2.  トランスポートをトランスポート バッファーに読み込むで次のコマンドを実行、`\usr\sap\trans\bin`ディレクトリと置換*sysid*開発システムのシステム id:  
  
        ```  
        tp addtobuffer <TransportNumber> <sysid> pf=TP_DOMAIN_<sysid>.PFL  
        ```  
  
         ここで、 *TransportNumber*実際のデータ転送数 (たとえば BI1K900534) です。  
  
    3.  後に、`tp`コマンドが終了したら、次のようなレポートが表示されます。  
  
        ```  
        This is tp version 320.56.66 (release 620)  
        Addtobuffer successful for TransportNumber  
        tp finished with return code: 0  
        ```  
  
         リターン コード「0」では、操作が成功したことを意味します。  
  
         0 または 4 のリターン コードは、許容されます。 8 またはそれより上位のリターン コードを受け取る場合は、Microsoft カスタマー サービス & サポートに問い合わせてください。  
  
        > [!IMPORTANT]
        >  手順 (b) と (c) をトランスポート ファイルの 2 番目のセットを繰り返します。  
  
        > [!NOTE]
        >  Cofile ファイル名から実際のデータ転送数を簡単に派生できます。 たとえば、cofile K900534 の名前です。BI1 は、BI1K900534 のトランスポートを提供します。  
  
3.  SAP トランスポートにインポートします。  
  
    1.  コマンド プロンプトで次のコマンドを実行します。  
  
        ```  
        tp import <TransportNumber> <sysid> client=<clientnumber> pf=TP_DOMAIN_<sysid>.PFL  
        ```  
  
         置き換える*sysid*開発システムのシステム id です。 置き換える*clientnumber*開発システムのクライアント数とします。  
  
         U2 パラメーターを使用すると、次のように、以前にインストールされているオブジェクトを上書きします。  
  
        ```  
        tp import <TransportNumber> <sysid> client=<clientnumber> U2  
        ```  
  
         または  
  
        ```  
        tp import <TransportNumber> <sysid> client=<clientnumber> pf=TP_DOMAIN_<sysid>.PFL U2  
        ```  
  
        > [!NOTE]
        >  Cofile ファイル名から実際のデータ転送数を簡単に派生できます。 たとえば、cofile K900534 の名前です。BI1 は、BI1K900534 のトランスポートを提供します。  
  
    2.  後に、`tp`コマンドが終了したら、次のようなレポートが表示されます。  
  
        ```  
        This is tp version 320.56.66 (release 620)  
        This is R3trans.exe version 6.08 (release 620 - 04.02.03 - 14:54:00).  
        R3trans.exe finished (0000).  
        This is R3trans.exe version 6.08 (release 620 - 04.02.03 - 14:54:00).  
        R3trans.exe finished (0000).  
        tp finished with return code: 0  
        ```  
  
         リターン コード「0」では、操作が成功したことを意味します。  
  
         0 または 4 のリターン コードは、許容されます。 8 またはそれより上位のリターン コードを受け取る場合は、Microsoft カスタマー サービス & サポートに問い合わせてください。  
  
        > [!IMPORTANT]
        >  転送ファイルの 2 番目のセットを手順 (a)、(b) を繰り返します。  
  
4.  トランスポート ログを確認します。  
  
5.  エラーがないことを確認するトランザクション SE09 を使用して、SAP GUI トランスポート開催者のトランスポート ログを確認します。  
  
 ユーザーの承認の設定  
 Z_EXTRACT_DATA_OO RFC には、特定の認証オブジェクトがユーザー Id が必要です。 SAP GUI 承認の管理ツールを使用して、RFC の実行に最低限の制限を設定します。  
  
> [!NOTE]
>  Z_EXECUTE_SAP_QUERY RFC の承認を設定する必要はありません。  
  
-   Z_EXTRACT_DATA_OO は S_TABU_DIS と Z_EIP_TABL の両方が必要です。 次の値は、システム内の任意のテーブルのメタデータを表示できるようにする S_TABU_DIS の最小制限を提供します。  
  
    -   ACTVT: 03  
  
    -   DICBERCLS: *  
  
     DICBERCLS を使用すると、承認クラスによってテーブルに承認を制限できます。  
  
     TDDAT テーブルを使用すると、テーブルの承認クラスを表示します。  
  
    > [!NOTE]
    >  テーブル メンテナンスのトランザクションによってテーブルに変更を防ぐため、実稼働環境での表示権限を付与する必要がありますのみ (ACTVT: 03 設定を表示する許容アクティビティ)。  
  
     Z_EIP_TABL の最小値は次のとおりです。  
  
    -   ACTVT: 03  
  
    -   テーブル: *  
  
     テーブルを使用すると、承認されているテーブルを明示的に定義します。 また、S_TABU_DIS が他のトランザクションでも使用されることに注意してください。  
  
##### <a name="to-set-user-authorization"></a>ユーザーの承認を設定するには  
  
1.  SAP の GUI を起動します。 コード、T 型に移動して`pfcg`、ENTER キーを押します。  
  
2.  **ロール**テキスト ボックスで、作成する、たとえば、ロール名を入力`ZTEST`、クリックして**ロール**です。  
  
3.  **Create Role**  ページで、をクリックして、**承認**タブです。  
  
     ロールを保存するメッセージが表示されたら、クリックして**はい**です。  
  
4.  **変更ロール** ページで、をクリックして、**変更の承認データ**ボタンをクリックします。  
  
5.  テンプレートを選択するメッセージが表示されたら、**テンプレートの選択**ダイアログ ボックスで、をクリックして**テンプレートを選択しない**です。  
  
6.  **ロールの変更: 承認** ページで、をクリックして、**手動で**ボタンをクリックします。  
  
7.  **承認の手動で選択**ボックスで、認証オブジェクトの名前を入力`Z_EIP_TABL`ENTER キーを押します。  
  
8.  **ロールの変更: 承認** ページで、テキスト ボックスが表示されるまでノードを展開して**アクティビティ**と**テーブル名**です。 **アクティビティ**テキスト ボックスに、値を入力`03`です。 **テーブル名**テキスト ボックスに、値を入力`*`です。  
  
9. クリックして、**保存**プロファイルを生成するボタンをクリックします。  
  
10. 戻り、**変更ロール**ページし、をクリックして、**ユーザー**タブです。  
  
11. **ユーザー**  タブで、ユーザー名を入力して、ロールのユーザー ID を割り当てる、**ユーザー ID**列、およびをクリックして、**ユーザー比較**ボタンをクリックします。  
  
12. **ロールのユーザーのマスター レコードの比較**、 をクリックして**比較が完了**マスター レコードを更新します。 ロールを保存するメッセージが表示されたら、クリックして**はい**です。  
  
13. 保存して閉じます。  
  
カスタム RFC のインストールを確認します。  
 カスタムの Rfc をインストールした後は、Rfc が正しくインストールされているかどうかを確認できます。  
  
-   Z_EXECUTE_SAP_QUERY RFC できるように SAP システムを使用して、定義済みのクエリを実行することによって、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]です。  
  
-   Z_EXTRACT_DATA_OO RFC の RFC が動作するが、システムで使用できる状態であることを確認するには、次のテストを実行することによってこれを実行できます。  
  
##### <a name="to-test-the-installation-of-zextractdataoo"></a>Z_EXTRACT_DATA_OO のインストールをテストするには  
  
1.  SAP GUI 承認の管理ツールで SE37、関数モジュール Z_EXTRACT_DATA_OO を実行し、テスト モードでキーを押して、RFC を実行`F8`です。 次のように、パラメーターを設定します。  
  
    |||  
    |-|-|  
    |IN_METADATA_ONLY||  
    |IN_METADATA_LANGUAGE|EN|  
    |IN_FROM_TABLE|T000|  
    |IN_OUTPUT_MODE|S|  
    |IN_OUTPUT_FILENAME||  
    |IN_USE_FIELD_EXITS|×|  
    |IN_SET_ROWCOUNT|0|  
    |IN_DELIMITER||  
    |IN_PACKET_SIZE|50,000|  
    |IN_MAX_WRITE_ATTEMPTS|4|  
    |IN_RETRY_DELAY|30|  
    |IN_SQL_DATES_ON||  
  
2.  をクリックして**Execute**またはキーを押して`F8`です。  
  
3.  結果ウィンドウで、次の手順を確認します。  
  
    |||  
    |-|-|  
    |OUT_TABLEHEADER|\<T000 一般的なメタデータ\>|  
    |OUT_TECHNICALSETTINGS|\<T000 技術的なデータベース レベルのメタデータ\>|  
    |OUT_RECORDLENGTH|\<SAP バージョンによって異なります\>|  
    |OUT_RECORDCOUNT|\<SE16 T000 を使用しているシステムでクライアントの数を確認します。\>|  
    |OUT_ZDATATABLE|\<T000 で SE 16 を使用して、ソース データと結果を確認します。\>|  
    |OUT_RETURN_TAB|S 001 成功|  
  
## <a name="remove-the-rfc-for-the-data-provider-for-sap"></a>SAP 用データ プロバイダーの RFC を削除します。  
  
1.  SAP GUI オブジェクト ナビゲーター (SE80) ZMSBI 開発クラスを使用したすべてのオブジェクトを検索します。  
  
2.  ディクショナリ オブジェクトの次のフォルダーから ZMSBI 開発クラスのすべてのオブジェクトを削除します。  
  
    -   構造体  
  
    -   関数のグループ  
  
    -   承認されたオブジェクト  
  
3.  トランスポート、させて、RFC (開発、テスト、および実稼働システムに、たとえば) がインストールされている各システムを移行します。  
  
     詳細については、SAP 単位管理者に問い合わせてください。  
     
## <a name="next"></a>Next
[BizTalk Adapter for mySAP Business Suite について](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)  
[SAP アダプター チュートリアル](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)