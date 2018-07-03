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
# <a name="install-custom-rfcs-for-the-data-provider-for-sap"></a>Data Provider for SAP のカスタム Rfc をインストールします。
MySAP Business Suite の SAP システムにアクセスする .NET Framework データ プロバイダーを使用する場合は、カスタム Rfc をインストールします。

[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]カスタム Rfc、SAP システムにいくつかの操作を実行する必要があります。
  
- 選択の操作を実行、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] Z_EXTRACT_DATA_OO RFC が必要です。  
  
- EXECQUERY 操作を実行、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] Z_EXECUTE_SAP_QUERY RFC が必要です。  
  
SAP システムでこれらの操作を実行するには、SAP システムでこれらのカスタム Rfc をインストールする必要があります。 インストールした場合、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]と共に、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]、セットアップ プログラムにコピーの RFC トランスポート、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]圧縮ファイルとして (customRFC.zip) システムでアダプターをインストールします。 Zip ファイルは通常にインストールされて*\<インストール ドライブ\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Microsoft .NET Framework Data Provider for mySAP Business Suite*します。 
  
 Zip ファイルを抽出するには、4 つのデータ ファイルが表示されます、次の名前付け、2 つのパターンを K9 *。BI1 (たとえば、K900534 に似ています。BI1)、およびその他の 2 つ R9 パターンに従う\*します。BI1 (たとえば、R900534 に似ています。BI1)。  
  

  
1. SAP アプリケーション サーバーに、アダプターを実行しているコンピューターから抽出したファイルをコピーします。  
  
   1.  開発システムの SAP アプリケーション サーバーに、SAP R/3 システムの管理者としてログインします。  
  
   2.  名前付けパターン K9 * で 2 つのトランスポート ファイルをコピーします。SAP アプリケーション サーバーで、次のディレクトリに、アダプターを実行しているコンピューター上のインストール ディレクトリから BI1:  
  
        `<drive>:\usr\sap\trans\cofiles`  
  
   3.  名前付けパターン R9 * で 2 つのトランスポート ファイルをコピーします。SAP アプリケーション サーバーで、次のディレクトリに、アダプターを実行しているコンピューター上のインストール ディレクトリから BI1:  
  
        `<drive>:\usr\sap\trans\data`  
  
2. SAP アプリケーション サーバー上のトランスポートのバッファーには、トランスポートを読み込みます。  
  
   1.  コマンド プロンプトでは、SAP アプリケーション サーバー上のトランスポート プログラム ディレクトリに移動します。  
  
        `<drive>:\usr\sap\trans\bin`  
  
   2.  トランスポートのバッファーには、トランスポートを読み込むで次のコマンドを実行、`\usr\sap\trans\bin`ディレクトリと置換*sysid*開発システムのシステム id:  
  
       ```  
       tp addtobuffer <TransportNumber> <sysid> pf=TP_DOMAIN_<sysid>.PFL  
       ```  
  
        ここで、 *TransportNumber*は実際のデータ転送の数 (たとえば BI1K900534) です。  
  
   3.  後に、`tp`コマンドが終了したら、次のようなレポートが表示されます。  
  
       ```  
       This is tp version 320.56.66 (release 620)  
       Addtobuffer successful for TransportNumber  
       tp finished with return code: 0  
       ```  
  
        リターン コード「0」は、操作が成功したことを意味します。  
  
        0 または 4 のリターン コードは、許容されます。 8 以降のリターン コードを受信する場合に Microsoft カスタマー サービス & サポート、お問い合わせください。  
  
       > [!IMPORTANT]
       >  手順 (b) と (c) をトランスポート ファイルの 2 番目のセットを繰り返します。  
  
       > [!NOTE]
       >  Cofile ファイル名から実際のデータ転送の数を簡単に派生できます。 たとえば、cofile K900534 の名前。BI1 は、BI1K900534 さまざまなトランスポートを提供します。  
  
3. SAP トランスポートにインポートします。  
  
   1.  コマンド プロンプトで次のコマンドを実行します。  
  
       ```  
       tp import <TransportNumber> <sysid> client=<clientnumber> pf=TP_DOMAIN_<sysid>.PFL  
       ```  
  
        置換*sysid*開発システムのシステム id。 置換*clientnumber*開発システムのクライアントの数。  
  
        次のように、以前にインストールされているオブジェクトを上書きするのに U2 パラメーターを使用することができます。  
  
       ```  
       tp import <TransportNumber> <sysid> client=<clientnumber> U2  
       ```  
  
        または  
  
       ```  
       tp import <TransportNumber> <sysid> client=<clientnumber> pf=TP_DOMAIN_<sysid>.PFL U2  
       ```  
  
       > [!NOTE]
       >  Cofile ファイル名から実際のデータ転送の数を簡単に派生できます。 たとえば、cofile K900534 の名前。BI1 は、BI1K900534 さまざまなトランスポートを提供します。  
  
   2.  後に、`tp`コマンドが終了したら、次のようなレポートが表示されます。  
  
       ```  
       This is tp version 320.56.66 (release 620)  
       This is R3trans.exe version 6.08 (release 620 - 04.02.03 - 14:54:00).  
       R3trans.exe finished (0000).  
       This is R3trans.exe version 6.08 (release 620 - 04.02.03 - 14:54:00).  
       R3trans.exe finished (0000).  
       tp finished with return code: 0  
       ```  
  
        リターン コード「0」は、操作が成功したことを意味します。  
  
        0 または 4 のリターン コードは、許容されます。 8 以降のリターン コードを受信する場合は、Microsoft カスタマー サービス & サポートに問い合わせてください。  
  
       > [!IMPORTANT]
       >  トランスポートのファイルの 2 番目のセットの手順 (a) および (b) を繰り返します。  
  
4. トランスポート ログを確認します。  
  
5. SAP GUI のトランスポート オーガナイザー SE09 トランザクションを使用して、エラーがないことを検証するトランスポート ログを確認します。  
  
   ユーザーの承認の設定  
   Z_EXTRACT_DATA_OO RFC では、特定の認証オブジェクトとユーザー Id が必要です。 RFC の実行に最低限の制限を設定するのにには、SAP GUI の承認管理ツールを使用します。  
  
> [!NOTE]
>  Z_EXECUTE_SAP_QUERY RFC の承認を設定する必要はありません。  
  
- Z_EXTRACT_DATA_OO は S_TABU_DIS と Z_EIP_TABL の両方が必要です。 次の値は、最小 S_TABU_DIS で、システム内の任意のテーブルのメタデータを表示できるように制限を提供します。  
  
  - ACTVT: 03  
  
  - DICBERCLS: *  
  
    DICBERCLS を使用して、承認クラスによってテーブルに承認を制限することができます。  
  
    TDDAT テーブルを使用すると、テーブルの承認クラスを表示します。  
  
  > [!NOTE]
  >  テーブル メンテナンスのトランザクションによってテーブルに変更を防ぐため、運用環境での表示権限を付与する必要がありますのみ (ACTVT: 03 設定を表示する許可されたアクティビティ)。  
  
   Z_EIP_TABL の最小値は次のとおりです。  
  
  - ACTVT: 03  
  
  - テーブル: *  
  
    承認済みのテーブルを明示的に定義するのにテーブルを使用することができます。 また、S_TABU_DIS が他のトランザクションにも使用します。  
  
##### <a name="to-set-user-authorization"></a>ユーザーの承認を設定するには  
  
1.  SAP GUI を起動します。 T コードの種類に移動して`pfcg`、ENTER キーを押します。  
  
2.  **ロール**テキスト ボックスなど、作成したいロールの名前を入力`ZTEST`、 をクリックし、**ロール**します。  
  
3.  **Create Role**  ページで、をクリックして、**承認**タブ。  
  
     ロールを保存するメッセージが表示されたら、クリックして**はい**します。  
  
4.  **変更ロール** ページで、をクリックして、**変更承認データ**ボタンをクリックします。  
  
5.  テンプレートを選択するメッセージが表示されたら、**テンプレートの選択**ダイアログ ボックスで、をクリックして**テンプレートを選択しないでください**します。  
  
6.  **ロールの変更: 承認** ページで、をクリックして、**手動で**ボタンをクリックします。  
  
7.  **承認の手動選択**承認オブジェクトの名前を入力ボックスに、 `Z_EIP_TABL` ENTER キーを押します。  
  
8.  **ロールの変更: 承認** ページで、テキスト ボックスが表示されるまでノードを展開して**アクティビティ**と**テーブル名**します。 **アクティビティ**テキスト ボックスに、値を入力`03`します。 **テーブル名**テキスト ボックスに、値を入力`*`します。  
  
9. をクリックして、**保存**プロファイルを生成するボタンをクリックします。  
  
10. 戻り、**変更ロール**ページ、をクリックし、**ユーザー**タブ。  
  
11. **ユーザー**  タブで、ユーザーの名前を入力して、ロールのユーザー ID を割り当てる、**ユーザー ID**列、およびクリック、**ユーザー比較**ボタンをクリックします。  
  
12. **ロールのユーザーのマスター レコードの比較**、 をクリックして**比較が完了**マスター レコードを更新します。 ロールを保存するメッセージが表示されたら、クリックして**はい**します。  
  
13. 保存して終了します。  
  
カスタム RFC のインストールを確認します。  
 カスタム Rfc をインストールした後は、Rfc が正しくインストールされているかどうかを確認できます。  
  
- Z_EXECUTE_SAP_QUERY rfc の場合は、これを行う SAP システムを使用して定義済みのクエリを実行することによって、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]します。  
  
- Z_EXTRACT_DATA_OO の rfc は、RFC が動作するが、システムで使用できる状態であることを確認するには、次のテストを実行することによってこれを実行できます。  
  
##### <a name="to-test-the-installation-of-zextractdataoo"></a>Z_EXTRACT_DATA_OO のインストールをテストするには  
  
1.  SAP GUI の承認管理ツールで SE37、関数モジュール Z_EXTRACT_DATA_OO を実行し、テスト モードでキーを押して、RFC を実行`F8`します。 次のように、パラメーターを設定します。  
  
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
  
2.  クリックして**Execute**またはキーを押します`F8`します。  
  
3.  結果ウィンドウで、次の手順を確認します。  
  
    |||  
    |-|-|  
    |OUT_TABLEHEADER|\<T000 一般的なメタデータ\>|  
    |OUT_TECHNICALSETTINGS|\<T000 テクニカル データベース レベルのメタデータ\>|  
    |OUT_RECORDLENGTH|\<SAP バージョンによって異なります\>|  
    |OUT_RECORDCOUNT|\<SE16 T000 を使用しているシステムでクライアントの数を確認します。\>|  
    |OUT_ZDATATABLE|\<T000 で SE 16 を使用してソース データでこの結果を確認します。\>|  
    |OUT_RETURN_TAB|S 001 成功|  
  
## <a name="remove-the-rfc-for-the-data-provider-for-sap"></a>Data Provider for SAP の RFC を削除します。  
  
1.  SAP GUI オブジェクト ナビゲーター (SE80) ZMSBI 開発のクラスを使用してすべてのオブジェクトを検索します。  
  
2.  Dictionary オブジェクトの次のフォルダーから ZMSBI 開発のクラスを使用してすべてのオブジェクトを削除します。  
  
    -   構造体  
  
    -   関数グループ  
  
    -   承認されたオブジェクト  
  
3.  トランスポートを生成し、RFC (開発、テスト、および実稼働システムに、たとえば) がインストールされている各システムを移行します。  
  
     詳細については、SAP 管理者に問い合わせてください。  
     
## <a name="next"></a>Next
[BizTalk Adapter for mySAP Business Suite について](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)  
[SAP アダプター チュートリアル](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)