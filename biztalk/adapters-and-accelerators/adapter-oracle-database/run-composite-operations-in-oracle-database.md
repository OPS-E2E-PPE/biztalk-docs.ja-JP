---
title: Oracle データベースで複合操作の実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b877d8e3-2016-40e8-888f-6b768021d6b8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a9728f456e6f3cf3ad95a392a5fdc45d6cf9265
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376119"
---
# <a name="run-composite-operations-in-oracle-database"></a>Oracle データベースで複合操作を実行します。
[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]により、任意の順序と、次の操作の任意の数を含めることができる複合操作を実行するクライアントはアダプター。  
  
- 選択、挿入、更新、およびテーブルとビューで操作を削除します。  
  
- ストアド プロシージャ、関数、およびプロシージャまたはアダプターでの操作として表示されるパッケージ内の関数。  
  
  複合操作の操作は、テーブルと同じデータベースまたは別のデータベース内のビューにターゲットします。 ただし、データを共有または複合操作のさまざまな操作で再利用することはできません。 たとえば、複合操作で Select 操作の結果セットは使えません入力パラメーターとしてストアド プロシージャの。  
  
  複合操作の各操作を実行するには、個別の接続を使用します。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]複合操作での操作の数は ODP.NET 接続プールからできるだけ多くの接続を消費し、取得、操作を実行するときに、接続を解放します。 ただし、複合操作内の操作では、結果セットを返しますの場合は、接続は、メッセージが消費した後にのみ解放されます。  
  
> [!IMPORTANT]
>  複合操作の実行中にタイムアウトの問題が発生した場合、可能性があります接続の数が、複合操作に関連する操作の数より少ない。  
> 
> - OUT、BFILE、BLOB、CLOB、NCLOB、および REF CURSOR を含むストアド プロシージャまたは IN OUT パラメーター。  
>   -   操作を選択します。  
> 
>   この問題を解決するには、複合操作では、このような操作の数を"n"がある場合は、値が指定を確認する必要があります、 **MinPoolSize** "n+1"プロパティをバインドは以上です。 詳細については、 **MinPoolSize**プロパティ、バインドを参照してください[for Oracle Database バインド プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)します。  
  
 詳細については。  
  
- 複合操作を実行する方法[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を使用して[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[を使用して BizTalk Server での Oracle データベースでの複合操作を実行](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md)します。  
  
- 複合操作のスキーマのメッセージを参照してください[複合操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md)します。  
  
## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)