---
title: SAP でプロバイダーによって使用されるカスタム Rfc |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Z_EXTRACT_DATA_OO, limitations related to
- RFC, Z_EXTRACT_DATA_OO
- Z_EXTRACT_DATA_OO
- Z_EXTRACT_DATA_OO, best practice
- Z_EXTRACT_DATA_OO, security issue
ms.assetid: 95661f4c-0431-40ca-8a53-3fbe359b8afd
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36b359fc893b8616fd4fb7339e9efbc42d7d3e13
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992723"
---
# <a name="custom-rfcs-used-by-the-provider-in-sap"></a>SAP でプロバイダーによって使用されるカスタム Rfc
[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SAP システムの操作を実行するために内部的に使用する次のカスタム Rfc を提供します。  
  
- **Z_EXTRACT_DATA_OO RFC**します。 データの抽出、RFC Z_EXTRACT_DATA_OO は、テーブルからデータを抽出、SAP R/3 システム ビューまたはデータ、および返すか、SQL Server テーブルの同期的にデータを変換します、またはフラット ファイルへのデータをダンプをします。 WHERE 句で SELECT 操作を実行する、Z_EXTRACT_DATA_OO が使用されます。 この RFC のパフォーマンスは、SAP システムのハードウェアに依存します。  
  
   Z_EXTRACT_DATA_OO RFC の .NET と SAP のデータ型をマップする方法については、次を参照してください。 [Data Type Mapping for カスタム Rfc](../../adapters-and-accelerators/adapter-sap/data-type-mapping-for-custom-rfcs.md)します。  
  
- **Z_EXECUTE_SAP_QUERY RFC**します。 この RFC を使って、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SAP システムで既に定義されているクエリを実行します。 この RFC では、内部的には、SAP の RFC RSAQ_REMOTE_QUERY_CALL を実行します。 SAP クエリは、テーブル、列、入力パラメーター、結果セットの並べ替え順序を選択して、SAP GUI を使用してグラフィカルに作成されるクエリです。使用して、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] ADO.NET クライアントからこのような SAP クエリを実行するようになりました。  
  
   EXECQUERY 操作によって返されるすべての値では、文字列型です。  
  
## <a name="limitations-related-to-the-zextractdataoo-rfc"></a>Z_EXTRACT_DATA_OO RFC に関する制限事項  
  
-   Z_EXTRACT_DATA_OO RFC では、次の条件を満たすテーブルからデータの読み取りがサポートされています。  
  
    -   テーブルの TabClass は TRANSP、クラスター、またはプールです。  
  
    -   TabClass はビューと ViewClass が D または P.  
  
-   Z_EXTRACT_DATA_OO HR クラスター テーブル、たとえば PCL1 PCL2、PCL3、PCL4 PCL5 をサポートしません。  
  
-   Z_EXTRACT_DATA_OO で抽出できる行の数は、SAP サーバーにハードウェア リソースに依存します。  
  
-   抽出されたすべてのデータは、主キーの順序で返されます。  
  
-   テーブルまたはビューの文字列、SSTRING および RAWSTRING の可変長データ型を含むはサポートされていません。 テーブルまたはビューのこれらのデータ型を含むを抽出することはできません。  
  
-   Z_EXTRACT_DATA_OO 変換終了が割り当てられているすべてのフィールドで変換が終了を実行します。 SELECT ステートメントの WHERE 句では、結果の変換後の値を入力してください。 変換後の値も返されます。 Z_EXTRACT_DATA_OO によって返される結果と SAP データ ブラウザー (SE16) で返される結果の間の不整合が発生する可能性があります。  
  
-   選択したテーブルには、ABAP (たとえば、接続) で予約された名前のフィールド名を含めることはできません。  
  
-   SAP R/3 バージョン 4.6 C 型の整数フィールドの値で、クエリ プロセッサでの制限により INT4 は WHERE 句での-999999999 以上である必要があります。 -999999999 よりも小さい INT4 値を持つ行は、値を含むフィールドが選択されているかどうかに関係なくは抽出されません。  
  
-   すべてのデータ値の型で SAP システムのバージョン 4.7 以上; で実行すると、WHERE 句は 256 文字に制限されています制限は、バージョン 4.6 c での 70 文字です。 生のデータ型の値をこれらの制限は 128 ~ 35 文字をそれぞれ半分は。 制限はありません RAW と LCHR のデータ型の長さで、結果として返されるときにします。  
  
-   SAP R/3 バージョン 4.6 C では、フィールド、where 句は 70 文字に制限されています。  
  
-   SAP R/3 バージョン 4.6 C では、すべてのテーブルを持つ出力の長さが 70 文字を超える主キー フィールドを抽出できません。  
  
-   SAP r/3 システム、バージョン 4.6 c、テーブルと可変長データ型を含むビューで (`VARC`) テーブルし、Z_EXTRACT_DATA_OO 関数の呼び出しを使用してデータ ソースからこれらのデータ型を抽出することはできませんを含むビューはサポートされていません。  
  
-   ファイルのモードで Z_EXTRACT_DATA_OO 関数の呼び出しを確認しないかどうかを変換先ファイルが既に開かれて、自体または別のアプリケーション。 そのため、関数できますを正しく記述しない開くファイルを同時に同じファイルにデータの追加中。 エラーは発生しません。  
  
-   ファイルのモードで Z_EXTRACT_DATA_OO 関数の呼び出しは、既存のファイルを上書きできます。 S_DATASET を使用してファイル システム アクセス Z_EXTRACT_DATA_OO を使用する SAP ユーザーが制限されていることを確認します。  
  
## <a name="security-considerations-with-the-custom-rfc"></a>カスタム RFC のセキュリティに関する考慮事項  
  
-   `Security Issue`: はそれらのファイルを保護するためサポートしていない場合は、フラット ファイルに書き込まれたデータを公開する可能性があります。  
  
     `Best practice`: フラット ファイル モードで Z_EXTRACT_DATA_OO 関数の呼び出しによってデータが書き込まれるファイル共有のセキュリティを強化します。  
  
-   `Security Issue`: ファイル モードで Z_EXTRACT_DATA_OO 関数の呼び出しを使用してに書き込まれる任意の共有上のファイルを上書きする可能性があります。 これは、SAP のドメイン アカウントがアクセスを持っている任意の共有上の任意のファイルに発生します。  
  
     `Best practice`: SAP のドメイン アカウントがアクセスを持っているすべての共有の保護に努めてください。  
  
-   `Security Issue`: ユーザーには、ターゲットが別の物理マシン上の場合、SAP アプリケーション サーバーからそのターゲット ファイル共有に転送中にデータを検査する (または「スニッフィング」) に機能があります。  
  
     `Best practice`: 通信を SAP サーバーとターゲット間でセキュリティを強化するため、IPsec または別の適切なメソッドを使用します。  
  
## <a name="see-also"></a>参照  
 [.NET Framework Data Provider for mySAP Business Suite について](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)