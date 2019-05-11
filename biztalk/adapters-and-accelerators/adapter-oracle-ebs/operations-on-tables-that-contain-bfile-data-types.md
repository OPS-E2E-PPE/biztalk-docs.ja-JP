---
title: BFILE データ型を含むテーブルで演算 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d7ebeb9-c2d6-4024-a169-263b947eeeb1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62ca4cecbc218497d18772103e538e71b32981bc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375286"
---
# <a name="operations-on-tables-that-contain-bfile-data-types"></a>BFILE データ型を含むテーブルに対する操作
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] BFILE データ型をテーブルとストアド プロシージャでサポートしています。 

## <a name="bfile-data-types"></a>BFILE データ型
次の表は、実行された操作に基づいて、アダプターによって公開される BFILE データ型と LOB 成果物 (テーブルまたはプロシージャ) アクセスをまとめたものです。  
  
|成果物|操作|BFILE col/パラメーターの公開されるデータ型|コメント|  
|--------------|---------------|--------------------------------------------|--------------|  
|TABLE|INSERT|String|BFILE 列に挿入するファイルに論理 Oracle ディレクトリ パスを表します<br /><br /> 例: Oracle での論理ディレクトリの MYDIR の MYDIR/screen.jpg|  
|TABLE|UPDATE|String|BFILE 列を更新するファイルに論理 Oracle ディレクトリ パスを表します|  
|TABLE|SELECT|byte[]|BFILE を構成するバイナリ データを表します|  
|ストアド プロシージャ|PARAM で|String|BFILE 列に挿入するファイルに論理 Oracle ディレクトリ パスを表します<br /><br /> 例: Oracle での論理ディレクトリの MYDIR の MYDIR/screen.jpg|  
|ストアド プロシージャ|OUT パラメーター|String|BFILE 列に挿入するファイルに論理 Oracle ディレクトリ パスを表します<br /><br /> 例: Oracle での論理ディレクトリの MYDIR の MYDIR/screen.jpg|  
|ストアド プロシージャ|INOUT パラメーター|サポートされていません|-|  
  
 特別な操作`Read_<LOBColName>`BFILE データ型を含むテーブルでサポートされても、 \<LOBColName\>テーブルに LOB 列名を指定します。 `Update_<LOBColName>` BFILE データ型の操作がサポートされていません。 アダプター クライアントは、更新操作を代わりに使用できます。  
  
## <a name="more-good-info"></a>詳細な情報  
  
-   `Read_<LOBColName>`と`Update_<LOBColName>`操作で、[インターフェイス テーブル、インターフェイス ビュー、テーブル、ビューを含む LOB データを操作](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)します。  
  
## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)