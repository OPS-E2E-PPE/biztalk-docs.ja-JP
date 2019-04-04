---
title: コンパイラ リンクを非表示にしたりする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66bfd9de-c4d2-46ee-854f-cf7c7cd07368
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3c006f5de761837ec1ed0d6f983d380a76a50a5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010051"
---
# <a name="how-to-show-and-hide-compiler-links"></a>コンパイラ リンクを表示する/非表示にする方法
マップをコンパイルすると、BizTalk マッパーにより、マップで必要となるすべてのリンクを示す追加のリンク (コンパイラ リンク) が作成されます。 これらのリンクのいくつかは、作成したリンクによって暗黙的に指定されます。 マップをコンパイルまたはテストする際、追加されたコンパイラ リンクをメイン ウィンドウに表示するかどうかを、Visual Studio の出力ウィンドウの最終行で選択できます。 既定では、コンパイラ リンクは赤色の波線で表示されます。  
  
### <a name="to-show-or-hide-compiler-links"></a>コンパイラ リンクの表示と非表示を切り替えるには  
  
1. ソリューション エクスプ ローラーでマップを表示する をクリックするコンパイラ リンクを右クリックして**マップのテスト**します。  
  
2. Visual Studio のエラー一覧 ウィンドウで最後にスクロールし、という行をダブルクリックします**ここをダブルクリックすると、コンパイラ リンクの表示/非表示に**します。  
  
    この行をもう一度クリックすると、コンパイラ リンクの表示と非表示が切り替わります。  
  
   > [!NOTE]
   >  場合を構築または再構築、BizTalk プロジェクトまたはソリューションの 1 つまたは複数のマップ、メッセージを格納している**ここをダブルクリックすると、コンパイラ リンクの表示/非表示に**に表示される、**エラー一覧**の Visual Studio のウィンドウプロジェクトまたはソリューションのすべてのマップ。  
  
   マップをテストするには、入力インスタンスおよび出力インスタンスのプロパティを構成する必要があります。 これらのプロパティを構成する方法の詳細については、[マップの検証の構成とテストのパラメーターは、方法](../core/how-to-configure-map-validation-and-test-parameters.md)を参照してください。  
  
## <a name="see-also"></a>参照  
 [リンクを使用してレコードとフィールド マッピングを指定する](../core/using-links-to-specify-record-and-field-mappings.md)