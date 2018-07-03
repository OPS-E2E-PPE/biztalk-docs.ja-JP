---
title: インターフェイス テーブルとインターフェイス ビューに対する操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6c7f3453-848f-42df-b092-725d9ff466cf
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffcf9b26f745112b4748c0020fd761f233caedd8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992035"
---
# <a name="operations-on-interface-tables-and-interface-views"></a>インターフェイス テーブルとインターフェイス ビューに対する操作
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]一連の標準的な操作 (Select、Insert、Update、および Delete の各インターフェイス テーブル) と Oracle E-business Suite には、各インターフェイス ビューの選択操作を表示します。 これらの操作を使用すると、SELECT、INSERT、UPDATE を実行し、対象のインターフェイス テーブル、WHERE 句で修飾されたステートメントおよび修飾対象のインターフェイス ビューの WHERE 句で SELECT ステートメントを削除できます。 これらの操作は、データ操作言語 (DML) 操作とも呼ばれます。  
  
> [!IMPORTANT]
>  インターフェイス テーブルとインターフェイス ビューで操作を実行する前に、アプリケーションのコンテキストでこれらの成果物を設定する必要があります[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 アプリケーション コンテキストの設定 (責任、組織、および言語の設定) などのユーザー設定とアーティファクトのアクセス制御を設定して Oracle E-business Suite でセキュリティで保護されたトランザクションを促進するためです。 アプリケーションのコンテキストとその設定方法の詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)します。  

## <a name="supported-dml-operations"></a>サポートされている DML 操作  
 次の表は、DML 操作を[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]をサポートしています。  
  
|演算|説明|  
|---------------|-----------------|  
|Select|指定された列の名前と SQL の WHERE 句を指定するフィルター文字列の一覧に基づいたターゲット インターフェイス テーブル、またはインターフェイス ビューで選択操作を行います。<br /><br /> Select 操作の戻り値は、指定した列と行を含む厳密に型指定された結果セットです。|  
|Insert|対象のインターフェイス テーブルに対する挿入操作を実行します。 Insert 操作サポートする複数のレコードは、指定されたレコード セットに基づく対象のインターフェイス テーブルに挿入します。<br /><br /> 挿入操作の戻り値では、挿入された行の数です。<br /><br /> **InlineValue**<br /><br /> という名前の省略可能な属性の値を指定することでレコードの値をオーバーライドする挿入操作ですべての単純なデータ レコードを選択できます**InlineValue**します。 日付列に主キー列 (SYSDATE を使用) のシステム日付を挿入するシーケンスを使用する、またはの設定などのインターフェイス テーブルに計算値を挿入する InlineValue 属性を使用できます。 たとえば、次のステートメントを挿入します。<br /><br /> `<Insert xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/AR/AR_ARCHIVE_PURGE_INTERIM">   <RECORDSET>     <InsertRecord xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/TableViewRecord/AR/AR_ARCHIVE_PURGE_INTERIM">       <TRNS_DATE InlineValue="sysdate">2008-06-21T15:52:19</TRNS_DATE>       <EMPNAME>John</EMPNAME>     </InsertRecord>   </RECORDSET>   </Insert>`<br /><br /> でも"2008-06-21T15:52:19"TRNS_DATE の値の値として指定されて、 **InlineValue**属性を"SYSDATE、"(システムの日付) は、対象のインターフェイス テーブルに挿入されます。<br /><br /> InlineValue の使用中に次のように属性します。<br /><br /> -InlineValue 属性の定数値を使用しないでください。 たとえば、INSERT ステートメントで指定した場合で`<EMPNAME InlineValue="John"/>`エラーが発生し、します。 として InlineValue 属性の値が渡されるため、これは-ここでは、Oracle に*John*が予期される値ではない Oracle E-business Suite に渡されます (期待される値は *"John"*)。 従業員名を囲む単一引用符を使用する必要があります。 たとえば、「 `<EMPNAME InlineValue="’John’"/>`」のように入力します。<br /><br /> -InlineValue 属性の選択クエリを使用する場合は、SELECT ステートメントをかっこで囲み、select クエリが 1 つのレコードのみをフェッチすることも確認する必要があります。 たとえば、「 `<EMPNAME InlineValue="(SELECT NAME FROM MS_SAMPLE_EMPLOYEES WHERE ID=123)"/>`」のように入力します。<br /><br /> **注:** 要素は、Oracle E-business Suite で NOT NULL としてマークすると、インラインの値を指定した場合でも、その要素の値を指定する必要があります。 失敗すると、スキーマ検証が失敗します。|  
|更新|対象のインターフェイス テーブル更新操作を実行します。 更新するレコードは、SQL の WHERE 句を指定するフィルター文字列によって指定されます。 更新プログラムの値は、テンプレートのレコードで指定されます。<br /><br /> 更新操作の戻り値では、更新された行の数です。|  
|DELETE|フィルター文字列で指定されている SQL の WHERE 句に基づいてターゲット インターフェイス テーブルに対して Delete 操作を実行します。<br /><br /> 削除操作の戻り値では、削除された行の数です。|  

## <a name="important-details"></a>重要な詳細情報  
- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]標準的な操作 (Select、Insert、Update、および、各テーブルの削除) と基になる Oracle データベース内の各ビューの選択操作の同じセットを表示します。 上記の DML 操作に対しても有効です、Oracle データベース テーブルの基になるとビュー。  

  - Oracle データベースでテーブルとビューで操作を実行するアプリケーションのコンテキストを設定する必要はありません。 ただし、カスタム Oracle E-business Suite アプリケーションでは、ユーザーは、ベース データベース テーブルにはインターフェイス テーブルとして登録できません。 データベース テーブルが、インターフェイス テーブルとして登録されていない場合で使用可能な**テーブル**でサブノード、**成果物ベース ビュー**ノードまたは、**スキーマ ベースのビュー**ノード使用しているときにデザイン時に[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
    これらのテーブルは、Oracle E-business アプリケーションに関連付けられます。 したがって、これらのテーブルの操作をアプリケーション コンテキストを設定する必要があります。 アプリケーション コンテキストの設定を参照してください。[ここリンクの説明を入力](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)します。  
  
## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)