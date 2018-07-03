---
title: テーブルと Oracle データベースで LOB データを格納するビューに対する操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data type
- binary file
- UpdateLOB
- ReadLOB
- LOB data types
- NCLOB
- large object
- binary large object
- CLOB
- national character large object
- BFILE
- BLOB
- character large object
ms.assetid: 25afd8c7-8ca3-4855-a231-2bec28c9a5cb
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a35be7008c47e46ca65962d113c4604c1cfad42b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984299"
---
# <a name="operations-on-tables-and-views-that-contain-lob-data-in-oracle-database"></a>テーブルと Oracle データベースで LOB データを格納するビューに対する操作
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle のラージ オブジェクト (LOB) データ型のサポートを提供します。  
  
- バイナリ ラージ オブジェクト (BLOB)  
  
- 文字ラージ オブジェクト (CLOB)  
  
- 各国語文字ラージ オブジェクト (NCLOB)  
  
- バイナリ ファイル (BFILE)。 詳細については、次を参照してください。 [BFILE データ型を含むテーブルに対する操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)します。  
  
  大量のデータを格納する Oracle データベースで LOB データ型の使用 (最大 4 GB)。 LOB 型では、入力と出力のストリーミングの両方をサポートします。  
  
  [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]サーフェスのテーブルとビューの LOB 列が含まれているは、次の操作。  
  
- **ReadLOB**します。 テーブルおよび BLOB、CLOB、NCLOB、BFILE、列を含むビューの ReadLOB 操作が表示されます。 ReadLOB オペレーションを使用してアダプターのクライアントは、データ ストリームとして LOB 列の値を読み取ることができます。 この操作は、LOB データ型の列名とフィルター文字列をパラメーターとして受け取ります。 アダプター クライアントは、フィルター文字列が正確に 1 つの一致する行をフェッチすることを確認する必要があります。 1 つ以上の一致する行がある場合、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]のみ (一致する) の最初の行の LOB 列が返されます。  
  
  > [!NOTE]
  >  ReadLOB 操作は、WCF サービス モデル内の LOB データの入力ストリームをサポートするために設計されています。 WCF チャネル モデルから LOB データを読み取るテーブルの選択操作を使用する必要がありますまたは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューション。 ストリーミングの詳細については、次を参照してください。 [Oracle データベースで LOB データ型のストリーミング サポート](../../adapters-and-accelerators/adapter-oracle-database/streaming-support-for-lob-data-types-in-oracle-database.md)します。  
  
- **UpdateLOB**します。 テーブルおよび BLOB、CLOB、NCLOB 列を含むビューの UpdateLOB 操作が表示されます。 UpdateLOB オペレーションを使用してアダプター クライアントは、LOB 列の値を更新できます。 この操作は LOB データ型の列名、フィルター文字列を受け取り、base64binary パラメーターとしてデータをエンコードします。 アダプター クライアントでは、フィルター文字列が 1 つだけ一致する行をフェッチを確認する必要があります。それ以外の場合、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] XmlReaderParsingException をスローします。  
  
  > [!NOTE]
  >  UpdateLOB 操作:  
  > 
  > - BFILE データ型のサポートされていません。 アダプター クライアントは、更新操作を使用してもできます。 詳細については、次を参照してください。 [BFILE データ型を含むテーブルに対する操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)します。  
  >   -   トランザクションの一部として実行する必要があります。 これは、確実に、 **UseAmbientTransaction**に設定するプロパティをバインドする必要があります**True**します。 については、 **UseAmbientTransaction**プロパティ、バインドを参照してください[for Oracle Database バインド プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)します。  
  
> [!NOTE]
>  ReadLOB と UpdateLOB は、1 つのテーブル行の 1 つの LOB 列を操作します。 複数の行の LOB 列または、単一行内の複数の LOB 列を操作するには、ターゲット各行に含まれる場合は、各ターゲット列に対して ReadLOB または UpdateLOB を呼び出す必要があります。  
  
 詳細については。  
  
- Oracle データベース テーブルを使用して、UpdateLOB 操作を呼び出す[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[を使用して BizTalk Server で大規模なオブジェクトの種類のデータ テーブルで操作を実行する](https://msdn.microsoft.com/library/cc185405(v=bts.10).aspx)します。 (で LOB データ型を読み取るテーブルの選択操作を使用する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)])。  
  
- WCF サービス モデルを使用して Oracle データベース テーブルで ReadLOB と UpdateLOB の操作を呼び出すを参照してください[WCF サービス モデルを使用して、大きなオブジェクトの型を持つテーブルでの操作を実行](../../adapters-and-accelerators/adapter-sql/read-or-update-tables-and-views-with-large-data-types-in-sql-with-a-wcf-service.md)します。  
  
- メッセージの構造と ReadLOB および UpdateLOB 操作を実行するための SOAP アクションを参照してください[特殊な LOB 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-special-lob-operations2.md)します。  
  
## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185259(v=bts.10).aspx)