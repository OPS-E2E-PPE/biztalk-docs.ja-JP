---
title: マップを使用しないでマップを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 520ec44f-5aca-4271-8835-b8e784214061
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c8d1ce3c42e1c776014036de7a832e8fd74b1be
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340037"
---
# <a name="how-to-create-a-map-without-maps"></a>マップを使用しないでマップを作成する方法
使用してインスタンス メッセージを変換する XSLT コードがある場合は、マップを作成するのではなく、直接そのコードを使用できます。  
  
 空のマップを作成および設定では、XSLT コードを使用してその**カスタム XSLT パス**グリッド プロパティ。 XSLT コードには、外部 .NET アセンブリを使用している場合は、カスタム拡張 XML ファイルを作成する必要があります。 カスタム拡張 XML ファイルの構造については、次を参照してください。、**カスタム拡張 XML (グリッド プロパティ)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
  
## <a name="use-custom-xslt-code-in-place-of-a-map"></a>マップの代わりにカスタムの XSLT コードを使用します。  
  
1.  プロジェクトに空の BizTalk マップを作成し、元と送信先スキーマを設定します。  
  
     マップを作成して、スキーマの設定については、次を参照してください。[マップの作成](../core/creating-maps.md)です。  
  
2.  グリッド ビューで、マッパー グリッドをクリックします。  
  
     プロパティ ウィンドウの表示、**グリッド**プロパティ。  
  
3.  [プロパティ] ウィンドウで次のように選択します**カスタム XSLT パス**、省略記号ボタンをクリックします ( **...** ) ボタンをクリックします。  
  
4.  **オープン** ダイアログ ボックスでファイルに移動し、をクリックして**オープン**します。  
  
     **カスタム XSLT パス**プロパティを設定します。  
  
> [!NOTE]
>  BizTalk マッパーでは、XSLT 1.0 はだけがサポートされます。 XSLT 2.0 の使用は、BizTalk マッパーではサポートされていません。  
  
## <a name="see-also"></a>参照  
 [マップについての詳細](../core/about-maps.md)   
 [使用してインライン XSLT および XSLT 呼び出しテンプレート スクリプト](../core/scripting-using-inline-xslt-and-xslt-call-templates.md)   
 [カスタム XSLT](../core/custom-xslt.md)   