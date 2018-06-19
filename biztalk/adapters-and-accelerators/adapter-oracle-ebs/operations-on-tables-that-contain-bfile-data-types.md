---
title: BFILE データ型を含むテーブルに対する操作 |Microsoft ドキュメント
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
ms.openlocfilehash: c5096539b86512e51756d3a872ff566872ff520f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961002"
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
  
 特別な操作`Read_<LOBColName>`BFILE データ型を持つテーブルでサポートされても、 \<LOBColName\>テーブルの LOB 列名を指定します。 `Update_<LOBColName>` BFILE データ型の操作がサポートされていません。 アダプターのクライアントは、更新操作を使用またはできます。  
  
## <a name="more-good-info"></a>詳細な情報  
  
-   `Read_<LOBColName>`と`Update_<LOBColName>`操作で、[インターフェイス テーブル、インターフェイス ビュー、テーブル、およびビューを含む LOB データに対する操作](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)です。  
  
## <a name="see-also"></a>参照  
 [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)