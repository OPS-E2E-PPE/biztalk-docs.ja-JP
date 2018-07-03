---
title: インターフェイス テーブル、インターフェイス ビュー、テーブル、および LOB データを格納するビューに対する操作 |Microsoft Docs
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
ms.openlocfilehash: 4f1336c1d6f5fb6ea7c0b68e4c7670616f141583
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967691"
---
# <a name="operations-on-interface-tables-interface-views-tables-and-views-that-contain-lob-data"></a>インターフェイス テーブル、インターフェイス ビュー、テーブル、および LOB データを格納するビューに対する操作
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] Oracle のラージ オブジェクト (LOB) データ型のサポートを提供します。  
  
- バイナリ ラージ オブジェクト (BLOB)  
  
- 文字ラージ オブジェクト (CLOB)  
  
- 各国語文字ラージ オブジェクト (NCLOB)  
  
- バイナリ ファイル (BFILE)。 詳細については、次を参照してください。[テーブルを含む BFILE データ型に対する演算](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)します。  
  
  基になる Oracle データベースで LOB データ型を使用して、大量のデータを格納する最大 4 ギガバイト (GB)。 BFILE データ型を除くは、LOB データ型は、入力と出力のストリーミングの両方をサポートします。  

## <a name="operations-for-tables-and-views"></a>テーブルおよびビューの操作  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サーフェスのインターフェイス テーブル、インターフェイス ビュー、テーブル、および LOB 列を含むビューの次の操作。  
  
- **Read_\<LOBColName\>**:`Read_<LOBColName>`インターフェイス テーブル、インターフェイス ビュー、テーブルおよび BLOB、CLOB、NCLOB、BFILE の列を含むビューの操作が表示される場所\<LOBColName\>か、BLOB、CLOB、NCLOB、BFILE、型の列の名前を指定します。 による、Read_\<LOBColName\>操作、アダプター クライアントはデータ ストリームとしての LOB 列の値を読み取ることができます。 この操作は、フィルター文字列をパラメーターとして受け取ります。  
  
  > [!NOTE]
  >  `Read_<LOBColName>`操作は、WCF サービス モデル内の LOB データの入力ストリームをサポートするために設計されています。 WCF チャネル モデルから LOB データを読み取るテーブルの選択操作を使用する必要がありますまたは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューション。  
  
- **Update_\<LOBColName\>**:`Update_<LOBColName>`インターフェイス テーブルとのみ列を含む BLOB、CLOB、NCLOB、テーブルの操作が表示される場所\<LOBColName\>の名前を指定します列は、BLOB、CLOB、NCLOB を入力します。 による、Update_\<LOBColName\>操作、アダプター クライアントは、LOB の列の値を更新できます。 BLOB データの種類の CLOB、NCLOB データ型で、この操作は、パラメーターとして文字列のフィルターは、この操作は、パラメーターとして base64binary でエンコードされたデータを受け取ります。  
  
  > [!NOTE]
  >  `Update_<LOBColName>`操作。  
  > 
  > - BFILE データ型のサポートされていません。 アダプター クライアントは、更新操作を使用してもできます。 詳細については、次を参照してください。[テーブルを含む BFILE データ型に対する演算](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)します。  
  >   -   公開されませんビューとビューのインターフェイスします。  
  >   -   トランザクションの一部として実行する必要があります。 これは、確実に、 **UseAmbientTransaction**に設定するプロパティをバインドする必要があります**True**します。 については、 **UseAmbientTransaction**プロパティ、バインドを参照してください[BizTalk Adapter for Oracle E-business Suite バインド プロパティの Rad](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。  
  
> [!IMPORTANT]
>  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サーフェスを`Read_<LOBColName>`と`Update_<LOBColName>`テーブル内の各 LOB 列を操作します。 そのため、(LOBCol1 および LOBCol2) テーブルに 2 つの LOB 列がある場合がある 2 つ`Read_<LOBColName>`操作 (Read_LOBCol1 および Read_LOBCol2) と 2 つの`Update_<LOBColName>`操作 (Update_LOBCol1 および Update_LOBCol2)。  
  
## <a name="more-good-info"></a>詳細な情報  
  
- 呼び出す、`Read_<LOBColName>`と`Update_<LOBColName>`Oracle E-business Suite を使用して基になるデータベースのテーブルに対する操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[大規模なデータ型を使用して BizTalk Server でのテーブルでの操作を実行](../../adapters-and-accelerators/adapter-sql/run-operations-on-tables-and-views-with-large-data-types-using-the-sql-adapter.md)します。  
  
- メッセージの構造体とを実行するための SOAP アクションの`Read_<LOBColName>`と`Update_<LOBColName>`操作で、[特殊な LOB 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-special-lob-operations1.md)します。  
  
## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)