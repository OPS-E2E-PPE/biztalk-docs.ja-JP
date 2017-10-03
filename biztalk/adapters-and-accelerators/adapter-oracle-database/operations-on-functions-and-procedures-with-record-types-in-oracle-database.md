---
title: "関数と Oracle データベースのレコードの種類を持つプロシージャに対する操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: RECORD type
ms.assetid: 28ecb76c-de82-43df-83cc-917c482417b3
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46daadeaa5d1fc1060217f044a9d143488c38d7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-functions-and-procedures-with-record-types-in-oracle-database"></a>関数と Oracle データベースのレコードの種類を持つプロシージャに対する操作
Oracle のレコードの種類は、PL/SQL 関数およびプロシージャに渡されるパラメーターで階層的な情報を表すために使用されます。 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]複雑な XML 型としてレコードの種類を表示します。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]次の種類のレコードの種類をサポートしています。  
  
-   ストアド プロシージャおよび関数では、テーブル %rowtype パラメーターとして宣言されているレコードの種類。  
  
-   たとえば、PL/SQL パッケージ内のレコードの型パラメーターとして宣言されているレコードの種類の入力 rec_type1 は RECORD(name varchar2(100), age number(3));  
  
-   入れ子になったレコードを含むレコードの種類。  
  
-   レコードに表示される型として、OUT、またはプロシージャまたは関数への OUT パラメーターです。  
  
-   関数の戻り値は、レコードの種類。  
  
    > [!NOTE]
    >  [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]レコードのメンバーとして BFILE 型をサポートしていません。  
  
 詳細については。  
  
-   関数または WCF サービス モデルを使用してレコードの種類に関連するプロシージャを呼び出してを参照してください[実行の操作を使用してレコードの種類、WCF サービス モデルを使用して Oracle データベース](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md)です。  
  
-   関数またはプロシージャのレコードに関連する型を使用して呼び出す[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[関数の呼び出しおよびレコードの種類を使用して BizTalk Server でのプロシージャ](../../adapters-and-accelerators/adapter-oracle-database/run-functions-and-procedures-with-record-types-in-oracle-db-with-biztalk-server.md)です。  
  
-   レコードの XML 構造の種類でサポートされている、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[レコードの種類のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-record-types.md)です。  
  
## <a name="see-also"></a>参照  
 [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)