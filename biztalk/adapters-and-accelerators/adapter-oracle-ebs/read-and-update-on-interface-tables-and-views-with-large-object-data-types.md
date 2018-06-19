---
title: インターフェイス テーブル、インターフェイス ビュー、テーブル、および LOB データを含むビューでの操作 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f6e8db6-ba68-4e3f-84b2-1cc31ce89bcb
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b12eeae422f5da90c6874f70d2ffddbc19f75bd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964704"
---
# <a name="operations-on-interface-tables-interface-views-tables-and-views-that-contain-lob-data"></a>インターフェイス テーブル、インターフェイス ビュー、テーブル、および LOB データを含むビューでの操作
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] Oracle ラージ オブジェクト (LOB) データ型のサポートを提供します。  
  
-   バイナリ ラージ オブジェクト (BLOB)  
  
-   文字ラージ オブジェクト (CLOB)  
  
-   各国語文字ラージ オブジェクト (NCLOB)  
  
-   バイナリ ファイル (BFILE)。 詳細については、次を参照してください。[テーブルを含む BFILE データ型の演算](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)です。  
  
 基になる Oracle データベースで LOB データ型が大量のデータの格納に使用される最大 4 ギガバイト (GB)。 BFILE データ型を除くは、LOB データ型は、入力と出力ストリームの両方をサポートします。  

## <a name="operations-for-tables-and-views"></a>テーブルやビューの操作  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]インターフェイス テーブル、インターフェイス ビュー、テーブルやビューの LOB 列を含む次の操作を表示します。  
  
-   **Read_\<LOBColName\>**:`Read_<LOBColName>`インターフェイス テーブル、インターフェイス ビュー、テーブルおよび BLOB、CLOB、NCLOB、BFILE の列を含むビューの操作が表示される場所\<LOBColName\>か、BLOB、CLOB、NCLOB、BFILE、型の列の名前を指定します。 による、Read_\<LOBColName\>操作、アダプターのクライアントはデータ ストリームとしての LOB 列の値を読み取ることができます。 この操作は、フィルター文字列をパラメーターとして受け取ります。  
  
    > [!NOTE]
    >  `Read_<LOBColName>`操作は、WCF サービス モデルでの LOB データの入力ストリーミングをサポートするために設計されています。 WCF チャネル モデルから LOB データを読み取るテーブルの選択操作を使用する必要がありますまたは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションです。  
  
-   **Update_\<LOBColName\>**:`Update_<LOBColName>`インターフェイス テーブルとのみ列を含む BLOB、CLOB、NCLOB、テーブルの操作が表示される場所\<LOBColName\>の名前を指定します。列は、BLOB、CLOB、NCLOB を入力します。 Update_ を使用して、\<LOBColName\>操作、アダプターのクライアントは、LOB の列の値を更新できます。 BLOB データ型のこの操作では CLOB や NCLOB データ型の場合は、この操作は、パラメーターとして文字列のフィルターをかかります。 一方、base64binary でエンコードされたデータをパラメーターとして受け取ります。  
  
    > [!NOTE]
    >  `Update_<LOBColName>`操作。  
    >   
    >  -   BFILE データ型のサポートされていません。 アダプターのクライアントは、更新操作を使用またはできます。 詳細については、次を参照してください。[テーブルを含む BFILE データ型の演算](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)です。  
    > -   公開されませんビューとビューのインターフェイスです。  
    > -   トランザクションの一部として実行する必要があります。 これには、ことを確認する、 **UseAmbientTransaction** binding プロパティを設定する必要があります**True**です。 については、 **UseAmbientTransaction**バインディング プロパティを参照してください[BizTalk Adapter for Oracle E-business Suite バインド プロパティに関する Rad](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。  
  
> [!IMPORTANT]
>  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サーフェス、`Read_<LOBColName>`と`Update_<LOBColName>`テーブル内の各 LOB 列を操作します。 そのため、(LOBCol1 および LOBCol2) テーブルに 2 つの LOB 列がある場合がある 2 つ`Read_<LOBColName>`操作 (Read_LOBCol1 および Read_LOBCol2) と 2 つの`Update_<LOBColName>`操作 (Update_LOBCol1 および Update_LOBCol2)。  
  
## <a name="more-good-info"></a>詳細な情報  
  
-   呼び出す、`Read_<LOBColName>`と`Update_<LOBColName>`Oracle E-business Suite を使用して基になるデータベース内のテーブルに対する操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[大規模なデータ型を使用して BizTalk Server を持つテーブルでの操作を実行](../../adapters-and-accelerators/adapter-sql/run-operations-on-tables-and-views-with-large-data-types-using-the-sql-adapter.md)です。  
  
-   メッセージの構造とを実行するための SOAP アクションの`Read_<LOBColName>`と`Update_<LOBColName>`操作で、[特別な LOB 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-special-lob-operations1.md)です。  
  
## <a name="see-also"></a>参照  
 [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)