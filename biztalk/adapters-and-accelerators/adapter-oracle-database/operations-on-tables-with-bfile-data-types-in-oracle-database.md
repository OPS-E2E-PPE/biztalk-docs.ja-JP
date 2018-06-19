---
title: Oracle データベースで BFILE データ型を持つテーブルに対する操作 |Microsoft ドキュメント
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
ms.openlocfilehash: c236651e6c44248ea8f6cf0f73f0c9bc17e46ac5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214314"
---
# <a name="operations-on-tables-with-bfile-data-types-in-oracle-database"></a>Oracle データベースで BFILE データ型を持つテーブルに対する操作
[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]テーブルやストアド プロシージャで BFILE データ型をサポートしています。 次の表は、実行操作に基づいて、アダプターによって公開される BFILE データ型と、LOB 成果物 (テーブルまたはプロシージャ) アクセスをまとめたものです。  
  
|成果物|操作|BFILE col/param の公開されているデータ型|コメント|  
|--------------|---------------|--------------------------------------------|--------------|  
|TABLE|INSERT|文字列|Oracle directory の論理パス ファイルを表す BFILE 列に挿入します。<br /><br /> 例: ここで、MYDIR は Oracle では、論理ディレクトリ MYDIR/screen.jpg|  
|TABLE|UPDATE|文字列|Oracle directory の論理パス ファイルを表す BFILE 列を更新するには|  
|TABLE|SELECT|byte[]|BFILE を構成するバイナリ データを表します|  
|ストアド プロシージャ|PARAM で|文字列|Oracle directory の論理パス ファイルを表す BFILE 列に挿入します。<br /><br /> 例: ここで、MYDIR は Oracle では、論理ディレクトリ MYDIR/screen.jpg|  
|ストアド プロシージャ|OUT パラメーター|文字列|Oracle directory の論理パス ファイルを表す BFILE 列に挿入します。<br /><br /> 例: ここで、MYDIR は Oracle では、論理ディレクトリ MYDIR/screen.jpg|  
|ストアド プロシージャ|INOUT パラメーター|サポートされていません|-|  
  
 特別な操作 ReadLOB は BFILE データ型を持つテーブルでもサポートされます。 UpdateLOB 操作はサポートされていません。 アダプターのクライアントは、更新操作を使用またはできます。  
  
 詳細については。  
  
-   BFILE データ型を使用して、含むテーブルでの操作を実行する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[BizTalk Server を使用して Oracle データベースで BFILE データ型を持つテーブルでの操作を実行](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-bfile-data-types-in-oracle-db-using-biztalk.md)です。  
  
## <a name="see-also"></a>参照  
 [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)