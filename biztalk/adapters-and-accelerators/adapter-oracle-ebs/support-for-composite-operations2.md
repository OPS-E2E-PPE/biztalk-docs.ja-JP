---
title: 複合 Operations2 のサポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3f65cf10-4e27-4872-bc6a-defe6cbab198
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 724d5bc41686abc3928716a0e08801107df25055
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979387"
---
# <a name="support-for-composite-operations"></a>複合操作のサポート
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]により、任意の順序と、次の操作の任意の数を含めることができる複合操作を実行するクライアントはアダプター。  
  
- 選択、挿入、更新、および、インターフェイス テーブルとデータベース テーブルでの操作を削除します。  
  
- インターフェイス ビューとデータベース ビューを操作を選択します。  
  
- ストアド プロシージャ、関数、およびアダプターでの操作として表示されるパッケージ内のプロシージャです。  
  
  複合操作の操作は、テーブルと同じデータベースまたは別のデータベース内のビューにターゲットします。 ただし、データを共有または複合操作のさまざまな操作で再利用することはできません。 たとえば、複合操作で Select 操作の結果セットは使えません入力パラメーターとしてストアド プロシージャの。  
  
  複合操作の各操作を実行するには、個別の接続を使用します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]複合操作での操作の数は ODP.NET 接続プールからできるだけ多くの接続を消費し、取得、操作を実行するときに、接続を解放します。 ただし、複合操作内の操作では、結果セットを返しますの場合は、接続は、メッセージが消費した後にのみ解放されます。  
  
> [!IMPORTANT]
>  複合操作の実行中にタイムアウトの問題が発生した場合、可能性があります接続の数が、複合操作に関連する操作の数より少ない。  
> 
> - OUT、BFILE、BLOB、CLOB、NCLOB、および REF CURSOR を含むストアド プロシージャまたは IN OUT パラメーター。  
>   -   操作を選択します。  
> 
>   この問題を解決するには、複合操作では、このような操作の数を"n"がある場合は、値が指定を確認する必要があります、 **MinPoolSize** "n+1"プロパティをバインドは以上です。 詳細については、 **MinPoolSize**プロパティ、バインドを参照してください[Oracle E-business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。  
  
 詳細については。  
  
- 複合操作を実行する方法[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を使用して[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[BizTalk Server を使用して Oracle データベースでの複合操作を実行](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md)します。  
  
- 複合操作のスキーマのメッセージを参照してください[複合操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-composite-operation1.md)します。  
  
> [!NOTE]
>  複合操作でのアプリケーションのコンテキストを設定することも、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 インターフェイス テーブル、またはインターフェイス ビューの複合操作の操作を実行する場合は、複合操作のアプリケーションのコンテキストを設定する必要があります。 アプリケーションのコンテキスト、および設定する方法については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)します。  
  
## <a name="see-also"></a>参照  
 [Oracle E-business Suite アダプターによってサポートされる操作](../../adapters-and-accelerators/adapter-oracle-ebs/what-operations-are-supported-by-the-oracle-e-business-suite-adapter.md)