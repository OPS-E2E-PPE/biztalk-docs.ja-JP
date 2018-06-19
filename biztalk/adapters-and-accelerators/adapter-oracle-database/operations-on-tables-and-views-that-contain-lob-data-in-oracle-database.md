---
title: テーブルと Oracle データベースでの LOB データを含むビューでの操作 |Microsoft ドキュメント
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
ms.openlocfilehash: ba5e110af598ac75ca9a8b6e7ebf2e5e8acc7aee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214394"
---
# <a name="operations-on-tables-and-views-that-contain-lob-data-in-oracle-database"></a>テーブルと Oracle データベースでの LOB データを含むビューでの操作
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle ラージ オブジェクト (LOB) データ型のサポートを提供します。  
  
-   バイナリ ラージ オブジェクト (BLOB)  
  
-   文字ラージ オブジェクト (CLOB)  
  
-   各国語文字ラージ オブジェクト (NCLOB)  
  
-   バイナリ ファイル (BFILE)。 詳細については、次を参照してください。 [BFILE データ型を含むテーブルでの操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)です。  
  
 大量のデータを格納する Oracle データベースに LOB データ型の使用 (4 GB まで)。 LOB 型では、入力と出力ストリームの両方をサポートします。  
  
 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]サーフェスのテーブルと LOB 列を含むビューの次の操作。  
  
-   **ReadLOB**です。 ReadLOB 操作は、テーブルおよび BLOB、CLOB、NCLOB、BFILE、列を含むビューを確認できます。 ReadLOB 操作を使用すると、アダプターのクライアントは、データ ストリームとしての LOB 列の値を読み取ることができます。 この操作は、LOB データ型の列名と、フィルター文字列をパラメーターとして受け取ります。 アダプターのクライアントでは、フィルター文字列が正確に 1 つの一致する行をフェッチすることを確認してください。 1 つ以上の一致する行がある場合、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]のみ (照合) の最初の行の LOB 列が返されます。  
  
    > [!NOTE]
    >  ReadLOB 操作は、WCF サービス モデルでの LOB データの入力ストリーミングをサポートするために設計されています。 WCF チャネル モデルから LOB データを読み取るテーブルの選択操作を使用する必要がありますまたは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションです。 ストリーミングの詳細については、次を参照してください。 [Oracle データベースでの LOB データ型のストリーミング サポート](../../adapters-and-accelerators/adapter-oracle-database/streaming-support-for-lob-data-types-in-oracle-database.md)です。  
  
-   **UpdateLOB**です。 UpdateLOB 操作は、テーブルおよび BLOB、CLOB、NCLOB 列を格納するビューを確認できます。 UpdateLOB 操作を使用すると、アダプターのクライアントは、LOB 列の値を更新できます。 この操作が LOB データ型の列名、フィルター文字列を受け取り、base64binary がパラメーターとしてデータをエンコードします。 アダプターのクライアントのフィルター文字列が; 1 つだけの一致する行をフェッチすることが保証されている必要があります。それ以外の場合、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] XmlReaderParsingException をスローします。  
  
    > [!NOTE]
    >  UpdateLOB 操作:  
    >   
    >  -   BFILE データ型のサポートされていません。 アダプターのクライアントは、更新操作を使用またはできます。 詳細については、次を参照してください。 [BFILE データ型を含むテーブルでの操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)です。  
    > -   トランザクションの一部として実行する必要があります。 これには、ことを確認する、 **UseAmbientTransaction** binding プロパティを設定する必要があります**True**です。 については、 **UseAmbientTransaction**バインディング プロパティを参照してください[Oracle データベースのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)です。  
  
> [!NOTE]
>  ReadLOB と UpdateLOB は、1 つのテーブルの行に 1 つの LOB 列で機能します。 または、単一行内の複数の LOB 列上で複数の行の LOB 列を操作するをターゲットの各行に含まれる各ターゲット列に対して ReadLOB または UpdateLOB を呼び出す必要があります。  
  
 詳細については。  
  
-   Oracle データベース テーブルを使用して、UpdateLOB 操作を呼び出す[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[を使用して BizTalk Server で大規模なオブジェクト型のデータを持つテーブルでの操作の実行](https://msdn.microsoft.com/library/cc185405(v=bts.10).aspx)です。 (テーブルの選択操作の LOB データ型の読み取りに使用する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)])。  
  
-   WCF サービスのモデルを使用して Oracle データベース テーブルで ReadLOB と UpdateLOB の操作を呼び出すことを参照してください[WCF サービス モデルを使用して大規模なオブジェクトの種類を持つテーブルでの操作を実行](../../adapters-and-accelerators/adapter-sql/read-or-update-tables-and-views-with-large-data-types-in-sql-with-a-wcf-service.md)です。  
  
-   メッセージの構造と ReadLOB および UpdateLOB 操作を実行するための SOAP アクションを参照してください[特別な LOB 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-special-lob-operations2.md)です。  
  
## <a name="see-also"></a>参照  
 [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185259(v=bts.10).aspx)