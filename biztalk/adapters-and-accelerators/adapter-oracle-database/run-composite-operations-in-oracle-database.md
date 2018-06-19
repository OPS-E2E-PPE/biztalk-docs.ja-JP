---
title: Oracle データベースで複合操作を実行 |Microsoft ドキュメント
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
ms.openlocfilehash: cd5595823fab4f25948e3d88db759ae525f62130
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215122"
---
# <a name="run-composite-operations-in-oracle-database"></a>Oracle データベースでの複合操作を実行します。
[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプター クライアントが、次の操作、および任意の順序で任意の数を含めることができる複合操作を実行できるようにします。  
  
-   選択、挿入、更新、およびテーブルとビューでの Delete 操作。  
  
-   ストアド プロシージャ、関数、およびプロシージャまたはアダプターでの操作として表示されたパッケージ内の関数。  
  
 複合操作内の操作対象に、同じデータベースまたは別のデータベースのテーブルおよびビューできます。 ただし、データを共有または複合操作のさまざまな操作間で再利用することはできません。 たとえば、操作では、複合、選択操作の結果セットは使えませんの入力パラメーターとしてストアド プロシージャの。  
  
 複合操作内の各操作は、別々 の接続を使用して実行されます。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]操作では、複合、操作の数として ODP.NET 接続プールからの複数の接続を使用し、操作が実行されると、接続を解放します。 ただし、複合操作の操作は、結果セットを返す場合、は、接続は、メッセージが処理した後にのみ解放されます。  
  
> [!IMPORTANT]
>  複合操作を実行中にタイムアウトの問題が発生した場合、可能性があります接続の数が関係する複合操作の操作の数より少ない。  
>   
>  -   BFILE、BLOB、CLOB、NCLOB、および REF CURSOR とアウトを含むストアド プロシージャまたは IN OUT パラメーターです。  
> -   操作を選択します。  
>   
>  この問題を解決するには、ある複合操作では、このような操作の"n"の数がある場合は、指定した値を確認する必要があります、 **MinPoolSize** "n+1"プロパティのバインドは以上です。 詳細については、 **MinPoolSize**バインディング プロパティを参照してください[Oracle データベースのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)です。  
  
 詳細については。  
  
-   複合操作を実行する方法[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を使用して[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[を使用して BizTalk Server での Oracle データベースでの複合操作を実行](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md)です。  
  
-   メッセージ複合操作のスキーマを参照してください[複合操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md)です。  
  
## <a name="see-also"></a>参照  
 [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)