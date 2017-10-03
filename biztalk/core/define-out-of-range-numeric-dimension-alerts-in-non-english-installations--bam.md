---
title: "英語以外のインストールで範囲外の数値ディメンション警告を定義する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7f1e0373-eadf-4c6d-9a38-a34d847f310f
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea63008680c026eded843e32a7b2c6ff26dc0bf0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-define-out-of-range-numeric-dimension-alerts-in-non-english-installations"></a>英語以外のインストールで範囲外の数値ディメンション警告を定義する方法
英語以外のインストールで定義されている数値範囲ディメンションの外部にある値を条件として含む警告を設定する場合は、文字列のローカライズ版を使用して BAM 定義を手動で変更する必要があります**範囲**.  
  
 範囲外を示すローカライズされた値の例を次の表に示します。  
  
|言語コード|ローカライズされた文字列|  
|-------------------|----------------------|  
|CN|超出范围|  
|DE|Außerhalb des gültigen Bereichs|  
|ES|Fuera de rango|  
|FR|hors limites|  
|IT|Fuori intervallo|  
|JA|範囲外|  
|KO|범위를 벗어남|  
|TW|超過範圍|  
  
### <a name="to-define-out-of-range-alerts-in-non-english-installations"></a>英語以外のインストールで範囲外の警告を定義するには  
  
1.  BAM 定義 xml ファイルが保存されているフォルダーに移動します。  
  
2.  テキスト エディターまたは XML エディターで、BAM 定義ファイルを開きます。  
  
3.  数値ディメンションに対応するスライサー ディメンションを探します。 たとえば、スライサー ディメンションの名前は**Alerts_NumDim**、次のノードを指定します。  
  
    ```  
    <SlicerDimension Name="Alerts_NumDim">  
    <Level Name="(Out of Range)" />  
    </SlicerDimension>  
    ```  
  
4.  変更、**範囲外の**文字列値を適切なローカライズされた文字列。  
  
5.  ファイルを保存して、定義を展開します。  
  
## <a name="see-also"></a>参照  
 [BAM 定義スキーマとは何ですか。](../core/what-is-a-bam-definition-schema.md)   
 [BAM 定義を展開する方法](../core/how-to-deploy-bam-definitions.md)