---
title: SAP のプロバイダーによって使用されるカスタム Rfc |Microsoft ドキュメント
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
ms.openlocfilehash: e55473dbcfeebecc504906d569c129989b054211
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216842"
---
# <a name="custom-rfcs-used-by-the-provider-in-sap"></a>SAP のプロバイダーによって使用されるカスタム Rfc
[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SAP システムでの操作を実行する内部で使用されているカスタム Rfc を提供します。  
  
-   **Z_EXTRACT_DATA_OO RFC**です。 データの抽出、RFC Z_EXTRACT_DATA_OO、テーブルからデータを抽出 SAP R/3 システム ビュー、データ、およびを返すか、SQL Server テーブルで同期的にデータを変換します。 またはフラット ファイルへのデータをダンプします。 Z_EXTRACT_DATA_OO を使用して、WHERE 句で SELECT 操作を実行できます。 この RFC のパフォーマンスは SAP システムのハードウェアに依存します。  
  
     Z_EXTRACT_DATA_OO RFC 用 .NET と SAP のデータ型をマップする方法については、次を参照してください。[カスタム Rfc のデータ型マッピング](../../adapters-and-accelerators/adapter-sap/data-type-mapping-for-custom-rfcs.md)です。  
  
-   **Z_EXECUTE_SAP_QUERY RFC**です。 この RFC を使って、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SAP システムで既に定義されているクエリを実行します。 この RFC では、SAP RFC、RSAQ_REMOTE_QUERY_CALL 内部的に実行します。 SAP クエリは、テーブル、列、入力パラメーター、結果セットの並べ替え順序を選択して、SAP GUI を使用してグラフィカルに作成されるクエリです。使用して、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] ADO.NET クライアントからこのような SAP クエリを実行するようになりました。  
  
     EXECQUERY 操作によって返されるすべての値では、文字列型です。  
  
## <a name="limitations-related-to-the-zextractdataoo-rfc"></a>Z_EXTRACT_DATA_OO RFC に関連する制限事項  
  
-   次の条件を満たすテーブルからデータを読み取る Z_EXTRACT_DATA_OO RFC をサポートします。  
  
    -   テーブルの TabClass は TRANSP、クラスター、またはプールです。  
  
    -   TabClass ビューは、ViewClass D または P. のいずれか  
  
-   Z_EXTRACT_DATA_OO は HR クラスター テーブル、たとえば PCL1 PCL2、PCL3、PCL4 PCL5 をサポートしていません。  
  
-   Z_EXTRACT_DATA_OO で抽出できる行の数は、SAP サーバー上のハードウェア リソースに依存します。  
  
-   主キーの順序では、すべての抽出データが返されます。  
  
-   テーブルまたはビューを含む文字列、SSTRING および RAWSTRING の可変長データ型はサポートされていません。 テーブルまたはビューのこれらのデータ型を含むを抽出することはできません。  
  
-   Z_EXTRACT_DATA_OO は変換終了します。 割り当てられているすべてのフィールドに変換が終了を実行します。 SELECT ステートメントの WHERE 句では、結果の変換後の値を入力してください。 変換された値も返されます。 Z_EXTRACT_DATA_OO によって返される結果と SAP データ ブラウザー (SE16) で返される結果との矛盾する可能性があります。  
  
-   選択したテーブルには、ABAP (たとえば、接続) で予約済みの名前は、フィールド名を含めることはできません。  
  
-   SAP R/3 バージョン 4.6 C 型の整数フィールドの値では、クエリ プロセッサに制限のため INT4 は、WHERE 句での-999999999 以上でなければなりません。 -999999999 よりも小さい INT4 値を持つ行は、値を含むフィールドが選択されているかどうかに関係なくは抽出されません。  
  
-   SAP システムのバージョン 4.7 以上; で実行されている場合は、WHERE 句が 256 文字に制限されます内のすべてのデータの値の型します。制限は、バージョン 4.6 c で 70 文字です。 生のデータ型の値のこれらの制限が半分に 128 ~ 35 文字をそれぞれします。 なしに制限は RAW モードおよび LCHR のデータ型の長さ、結果として返されるときにします。  
  
-   SAP R/3 バージョン 4.6 C WHERE 句でのフィールドでは、句は、70 文字に制限されます。  
  
-   SAP R/3 バージョン 4.6 C では、すべてのテーブルを持つ出力の長さが 70 文字を超える主キー フィールドを抽出できません。  
  
-   SAP R/3 バージョン 4.6 c、テーブルと可変長データ型を含むビュー (`VARC`) はサポートされていませんし、テーブルし、ビューを含む Z_EXTRACT_DATA_OO 関数呼び出しを使用してデータ ソースからこれらのデータ型を抽出することはできません。  
  
-   ファイル モードで Z_EXTRACT_DATA_OO 関数呼び出しをチェックしないかどうか、コピー先ファイルは既に開かれて、単独または他のアプリケーション。 そのため、関数は、正しく記述できましていない開いているファイルへ同時に同じファイルにデータの追加中。 エラーは発生しません。  
  
-   ファイル モードで Z_EXTRACT_DATA_OO 関数呼び出しは、既存のファイルを上書きできます。 Z_EXTRACT_DATA_OO を使用する SAP ユーザーが S_DATASET を使用してファイル システムへのアクセスを制限することを確認します。  
  
## <a name="security-considerations-with-the-custom-rfc"></a>カスタムの RFC にセキュリティの考慮事項  
  
-   `Security Issue`: はそれらのファイルを保護する役立たない場合、フラット ファイルに書き込まれたデータを公開する可能性があります。  
  
     `Best practice`: フラット ファイル モードで Z_EXTRACT_DATA_OO 関数呼び出しによってデータが書き込まれるファイル共有のセキュリティを強化します。  
  
-   `Security Issue`: 可能性がある Z_EXTRACT_DATA_OO 関数呼び出しを使用してファイル モードで書き込むことができる任意の共有にファイルを上書きします。 これは、SAP のドメイン アカウントがアクセスしている任意の共有上の任意のファイルに発生することができます。  
  
     `Best practice`: SAP ドメイン アカウントがアクセスしているすべての共有の保護に努めています。  
  
-   `Security Issue`: ユーザーでは、状況で、ターゲットが異なる物理コンピューターには、SAP アプリケーション サーバーから、対象のファイル共有への転送中にデータを検査 (または「傍受」) に機能があります。  
  
     `Best practice`: SAP サーバーとターゲットの間でより安全な通信を行うため、IPsec または別の適切なメソッドを使用します。  
  
## <a name="see-also"></a>参照  
 [.NET Framework Data Provider for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)