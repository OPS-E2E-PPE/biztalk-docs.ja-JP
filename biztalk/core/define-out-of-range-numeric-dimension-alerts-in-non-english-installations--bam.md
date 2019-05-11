---
title: 英語以外のインストールで範囲外の数値ディメンション警告を定義する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f1e0373-eadf-4c6d-9a38-a34d847f310f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 703c59f83e0a9af01bcddbea1358a56aa825037b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352484"
---
# <a name="how-to-define-out-of-range-numeric-dimension-alerts-in-non-english-installations"></a>英語以外のインストールで範囲外の数値ディメンション警告を定義する方法
英語以外のインストールで定義されている数値範囲ディメンション外の値を条件として含むアラートを設定するときに、文字列のローカライズされたバージョンと、BAM 定義を手動で変更する必要があります**の範囲外**.  
  
 次の表では、ローカライズされた範囲外の値の例を示します。  
  
|言語コード|ローカライズされた文字列|  
|-------------------|----------------------|  
|CN|超出范围|  
|DE|Außerhalb des gültigen Bereichs|  
|ES|Fuera de rango|  
|FR|hors で|  
|その|Fuori intervallo|  
|JA|範囲外|  
|KO|범위를 벗어남|  
|TW|超過範圍|  
  
### <a name="to-define-out-of-range-alerts-in-non-english-installations"></a>英語以外のインストールで範囲外のアラートを定義するには  
  
1.  BAM 定義 xml ファイルを含むフォルダーに移動します。  
  
2.  テキスト エディターまたは XML エディターを使用して、BAM 定義ファイルを開きます。  
  
3.  数値のディメンションのスライサー ディメンションを探します。 たとえば、スライサー ディメンションの名前は**Alerts_NumDim**、次のノードを検索する場合します。  
  
    ```  
    <SlicerDimension Name="Alerts_NumDim">  
    <Level Name="(Out of Range)" />  
    </SlicerDimension>  
    ```  
  
4.  変更、 **Out of Range**を適切な文字列値がローカライズされた文字列。  
  
5.  ファイルを保存し、定義を展開します。  
  
## <a name="see-also"></a>参照  
 [BAM 定義スキーマとは何ですか。](../core/what-is-a-bam-definition-schema.md)   
 [BAM 定義を展開する方法](../core/how-to-deploy-bam-definitions.md)