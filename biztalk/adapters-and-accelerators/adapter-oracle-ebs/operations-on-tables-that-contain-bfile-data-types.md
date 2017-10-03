---
title: "BFILE データ型を含むテーブルに対する操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d7ebeb9-c2d6-4024-a169-263b947eeeb1
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 122d821754fb6df447067d18f6f5da02b79058e4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-tables-that-contain-bfile-data-types"></a>BFILE データ型を含むテーブルでの操作
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]テーブルやストアド プロシージャで BFILE データ型をサポートしています。 

## <a name="bfile-data-types"></a>BFILE データ型
次の表は、実行操作に基づいて、アダプターによって公開される BFILE データ型と、LOB 成果物 (テーブルまたはプロシージャ) アクセスをまとめたものです。  
  
|成果物|操作|BFILE col/param の公開されているデータ型|コメント|  
|--------------|---------------|--------------------------------------------|--------------|  
|TABLE|INSERT|文字列|Oracle directory の論理パス ファイルを表す BFILE 列に挿入します。<br /><br /> 例: ここで、MYDIR は Oracle では、論理ディレクトリ MYDIR/screen.jpg|  
|TABLE|UPDATE|文字列|Oracle directory の論理パス ファイルを表す BFILE 列を更新するには|  
|TABLE|SELECT|byte[]|BFILE を構成するバイナリ データを表します|  
|ストアド プロシージャ|PARAM で|文字列|Oracle directory の論理パス ファイルを表す BFILE 列に挿入します。<br /><br /> 例: ここで、MYDIR は Oracle では、論理ディレクトリ MYDIR/screen.jpg|  
|ストアド プロシージャ|OUT パラメーター|文字列|Oracle directory の論理パス ファイルを表す BFILE 列に挿入します。<br /><br /> 例: ここで、MYDIR は Oracle では、論理ディレクトリ MYDIR/screen.jpg|  
|ストアド プロシージャ|INOUT パラメーター|サポートされていません|-|  
  
 特別な操作`Read_<LOBColName>`BFILE データ型を持つテーブルでサポートされても、 \<LOBColName > テーブルの LOB 列名を指定します。 `Update_<LOBColName>` BFILE データ型の操作がサポートされていません。 アダプターのクライアントは、更新操作を使用またはできます。  
  
## <a name="more-good-info"></a>詳細な情報  
  
-   `Read_<LOBColName>`と`Update_<LOBColName>`操作で、[インターフェイス テーブル、インターフェイス ビュー、テーブル、およびビューを含む LOB データに対する操作](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)です。  
  
## <a name="see-also"></a>参照  
 [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)