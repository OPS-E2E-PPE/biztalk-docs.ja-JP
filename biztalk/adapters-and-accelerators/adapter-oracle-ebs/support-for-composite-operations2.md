---
title: "複合 Operations2 のサポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f65cf10-4e27-4872-bc6a-defe6cbab198
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5766adec70c1a1fe7eaabe4ffaf07499e33d210c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="support-for-composite-operations"></a>複合操作のサポート
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アダプター クライアントが、次の操作、および任意の順序で任意の数を含めることができる複合操作を実行できるようにします。  
  
-   選択、挿入、更新、およびインターフェイス テーブルおよびデータベースのテーブルに対する操作を削除します。  
  
-   インターフェイス ビューとデータベース ビューに操作を選択します。  
  
-   ストアド プロシージャ、関数、およびアダプターでの操作として表示されたパッケージ内のプロシージャです。  
  
 複合操作内の操作対象に、同じデータベースまたは別のデータベースのテーブルおよびビューできます。 ただし、データを共有または複合操作のさまざまな操作間で再利用することはできません。 たとえば、操作では、複合、選択操作の結果セットは使えませんの入力パラメーターとしてストアド プロシージャの。  
  
 複合操作内の各操作は、別々 の接続を使用して実行されます。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]操作では、複合、操作の数として ODP.NET 接続プールからの複数の接続を使用し、操作が実行されると、接続を解放します。 ただし、複合操作の操作は、結果セットを返す場合、は、接続は、メッセージが処理した後にのみ解放されます。  
  
> [!IMPORTANT]
>  複合操作を実行中にタイムアウトの問題が発生した場合、可能性があります接続の数が関係する複合操作の操作の数より少ない。  
>   
>  -   BFILE、BLOB、CLOB、NCLOB、および REF CURSOR とアウトを含むストアド プロシージャまたは IN OUT パラメーターです。  
> -   操作を選択します。  
>   
>  この問題を解決するには、ある複合操作では、このような操作の"n"の数がある場合は、指定した値を確認する必要があります、 **MinPoolSize** "n+1"プロパティのバインドは以上です。 詳細については、 **MinPoolSize**バインディング プロパティを参照してください[Oracle E-business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。  
  
 詳細については。  
  
-   複合操作を実行する方法[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を使用して[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[BizTalk Server を使用して Oracle データベースでの複合操作を実行](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md)です。  
  
-   メッセージ複合操作のスキーマを参照してください[複合操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-composite-operation1.md)です。  
  
> [!NOTE]
>  複合の操作でアプリケーションのコンテキストを設定することも、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 必須ではインターフェイス テーブルまたはインターフェイス ビューでの複合操作で操作を実行する場合は、複合操作のアプリケーション コンテキストを設定します。 アプリケーションのコンテキスト、およびように設定する方法については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。  
  
## <a name="see-also"></a>参照  
 [どのような操作、Oracle E-business Suite アダプターによってサポートされます。](../../adapters-and-accelerators/adapter-oracle-ebs/what-operations-are-supported-by-the-oracle-e-business-suite-adapter.md)