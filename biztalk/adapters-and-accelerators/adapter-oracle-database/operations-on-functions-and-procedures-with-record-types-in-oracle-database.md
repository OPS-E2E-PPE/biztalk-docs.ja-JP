---
title: Oracle データベースのレコードの種類で関数とプロシージャに対する操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RECORD type
ms.assetid: 28ecb76c-de82-43df-83cc-917c482417b3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2635ac4b21173fe1a12603c60263dfa70b5a18e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974203"
---
# <a name="operations-on-functions-and-procedures-with-record-types-in-oracle-database"></a>Oracle データベースのレコードの種類で関数とプロシージャに対する操作
Oracle のレコードの種類は、PL/SQL 関数およびプロシージャに渡されるパラメーターで階層的な情報を表すために使用されます。 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]サーフェスの複雑な XML 型としてレコードの種類。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]次の種類のレコードの種類をサポートしています。  
  
- ストアド プロシージャおよび関数でテーブル %rowtype パラメーターとして宣言されているレコードの種類。  
  
- たとえば、PL/SQL パッケージ内のレコードの型パラメーターとして宣言されているレコードの種類の入力 rec_type1 は RECORD(name varchar2(100), age number(3));  
  
- 入れ子になったレコードを含むレコードの種類。  
  
- OUT、IN として表示されるレコードの種類またはプロシージャまたは関数への OUT パラメーター。  
  
- 関数の戻り値であるレコードの種類。  
  
  > [!NOTE]
  >  [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]レコードのメンバーとして BFILE 型をサポートしていません。  
  
  詳細については。  
  
- 関数または WCF サービス モデルを使用してレコードの種類に関連するプロシージャを呼び出しを参照してください[実行の操作を使用してレコードの種類、WCF サービス モデルを使用して Oracle データベース](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md)します。  
  
- 関数またはプロシージャのレコードに関連する型を使用して呼び出す[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[を使用して BizTalk Server でのレコードの種類で呼び出す関数とプロシージャ](../../adapters-and-accelerators/adapter-oracle-database/run-functions-and-procedures-with-record-types-in-oracle-db-with-biztalk-server.md)します。  
  
- レコードの XML 構造の種類でサポートされている、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[レコードの種類のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-record-types.md)します。  
  
## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)