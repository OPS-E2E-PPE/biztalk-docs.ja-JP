---
title: Oracle データベースで BFILE データ型を持つテーブルに対する操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operations, on tables with BFILE data types
- BFILE data type
- BFILE
ms.assetid: 7937564e-4423-459f-9824-6a27113ebfb3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab9885497468f91b309eb51ac0abbf4c0807ca76
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998259"
---
# <a name="operations-on-tables-with-bfile-data-types-in-oracle-database"></a>Oracle データベースで BFILE データ型を持つテーブルに対する操作
[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] BFILE データ型をテーブルとストアド プロシージャでサポートしています。 次の表は、実行された操作に基づいて、アダプターによって公開される BFILE データ型と LOB 成果物 (テーブルまたはプロシージャ) アクセスをまとめたものです。  
  
|成果物|演算|BFILE col/パラメーターの公開されるデータ型|コメント|  
|--------------|---------------|--------------------------------------------|--------------|  
|TABLE|INSERT|String|BFILE 列に挿入するファイルに論理 Oracle ディレクトリ パスを表します<br /><br /> 例: Oracle での論理ディレクトリの MYDIR の MYDIR/screen.jpg|  
|TABLE|UPDATE|String|BFILE 列を更新するファイルに論理 Oracle ディレクトリ パスを表します|  
|TABLE|SELECT|byte[]|BFILE を構成するバイナリ データを表します|  
|ストアド プロシージャ|PARAM で|String|BFILE 列に挿入するファイルに論理 Oracle ディレクトリ パスを表します<br /><br /> 例: Oracle での論理ディレクトリの MYDIR の MYDIR/screen.jpg|  
|ストアド プロシージャ|OUT パラメーター|String|BFILE 列に挿入するファイルに論理 Oracle ディレクトリ パスを表します<br /><br /> 例: Oracle での論理ディレクトリの MYDIR の MYDIR/screen.jpg|  
|ストアド プロシージャ|INOUT パラメーター|サポートされていません|-|  
  
 特別な操作 ReadLOB は BFILE データ型を持つテーブルでもサポートされます。 UpdateLOB 操作がサポートされていません。 アダプター クライアントは、更新操作を代わりに使用できます。  
  
 詳細については。  
  
- 使用して BFILE データ型を含むテーブルでの操作を実行する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[BizTalk Server を使用して Oracle データベースで BFILE データ型を持つテーブルに対する操作を実行](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-bfile-data-types-in-oracle-db-using-biztalk.md)します。  
  
## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)