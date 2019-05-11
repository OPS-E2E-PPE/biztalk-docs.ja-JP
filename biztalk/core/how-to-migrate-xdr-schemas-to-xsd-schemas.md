---
title: XDR スキーマを XSD スキーマに移行する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 90bde0d0-bfe6-4d6c-823c-8ed9c0e15783
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee5394b0a4b761e1dc650cfa41e10822d856895a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384641"
---
# <a name="how-to-migrate-xdr-schemas-to-xsd-schemas"></a>XDR スキーマを XSD スキーマに移行する方法
BizTalk Server の以前のバージョンからスキーマを移行する場合は、Xml-data Reduced (XDR) スキーマを XML スキーマ定義 (XSD) 言語スキーマに変換する必要があります。 このトピックでは、必要な手順について説明します。  
  
### <a name="to-generate-an-xsd-schema-from-an-xdr-schema"></a>XDR スキーマから XSD スキーマを生成するには  
  
1.  **ソリューション エクスプ ローラー**、関連する BizTalk プロジェクトを右クリックし、 をポイント**追加**、 をクリックし、**生成した項目の追加**します。  
  
2.  **生成項目の追加 - \< *BizTalk ProjectName* \>**   ダイアログ ボックスで、**テンプレート**セクションで、**生成スキーマ**、 をクリックし、**追加**します。  
  
3.  **スキーマの生成**] ダイアログ ボックスで、**ドキュメントの種類**一覧で、[ **XDR スキーマ**します。  
  
4.  をクリックして**参照**、クリックして、移行する XDR スキーマ ファイルを見つけます**OK**します。  
  
     新しいスキーマは、指定した XDR スキーマ ファイル、したファイル拡張子は .xsd と同じ名前を使用して、BizTalk エディターで開かれたから生成されます。  
  
> [!NOTE]
>  使用しないでくださいC#スキーマ ルート ノード名、またはファイル名として単語や .NET Framework 型と名前空間の名前 (System など) に予約されています。  
  
## <a name="see-also"></a>参照  
 [プロジェクト内のスキーマを管理します。](../core/managing-schemas-within-projects.md)   
 [フラット ファイル レコードの移行](../core/migrating-flat-file-records.md)