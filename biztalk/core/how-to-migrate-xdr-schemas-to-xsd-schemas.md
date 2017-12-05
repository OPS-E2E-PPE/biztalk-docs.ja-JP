---
title: "XDR スキーマを XSD スキーマに移行する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90bde0d0-bfe6-4d6c-823c-8ed9c0e15783
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84bbc42297a10c7d42adb8d778ba19b3b392742c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-migrate-xdr-schemas-to-xsd-schemas"></a>XDR スキーマを XSD スキーマに移行する方法
以前のバージョンの BizTalk Server のスキーマを移行する場合、XDR (XML-Data Reduced) スキーマを XSD (XML Schema Definition) 言語スキーマに変換する必要があります。 このトピックでは、必要な手順について説明します。  
  
### <a name="to-generate-an-xsd-schema-from-an-xdr-schema"></a>XDR スキーマから XSD スキーマを生成するには  
  
1.  **ソリューション エクスプ ローラー**、関連する BizTalk プロジェクトを右クリックし、順にポイント**追加**、クリックして**生成した項目の追加**です。  
  
2.  **生成項目の追加 - \<* BizTalk ProjectName*\>* * ダイアログ ボックスで、**テンプレート**セクションで、**生成スキーマ**、クリックして**追加**です。  
  
3.  **スキーマの生成**] ダイアログ ボックスで、**ドキュメントの種類**一覧で、[ **XDR スキーマ**です。  
  
4.  をクリックして**参照**、クリックして、移行する XDR スキーマ ファイルを見つけます**OK**です。  
  
     指定した XDR スキーマ ファイルから新しいスキーマが生成され、BizTalk エディターに表示されます。スキーマ名には、指定したファイルと同じ名前 (拡張子は .xsd) が使用されます。  
  
> [!NOTE]
>  スキーマ ルート ノード名またはファイル名に対して、C# 予約語、.NET Framework 型、および名前空間名 (System など) を使用しないでください。  
  
## <a name="see-also"></a>参照  
 [プロジェクト内のスキーマを管理します。](../core/managing-schemas-within-projects.md)   
 [フラット ファイル レコードの移行](../core/migrating-flat-file-records.md)