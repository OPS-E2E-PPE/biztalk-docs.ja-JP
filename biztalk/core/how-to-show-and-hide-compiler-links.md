---
title: コンパイラ リンクを非表示にしたりする方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 66d9b9ee8901ea2d93a73fd227a0ac1623e25669
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255546"
---
# <a name="how-to-show-and-hide-compiler-links"></a>コンパイラ リンクを表示する/非表示にする方法
マップをコンパイルすると、BizTalk マッパーにより、マップで必要となるすべてのリンクを示す追加のリンク (コンパイラ リンク) が作成されます。 これらのリンクのいくつかは、作成したリンクによって暗黙的に指定されます。 マップをコンパイルまたはテストする際、追加されたコンパイラ リンクをメイン ウィンドウに表示するかどうかを、Visual Studio の出力ウィンドウの最終行で選択できます。 既定では、コンパイラ リンクは赤色の波線で表示されます。  
  
### <a name="to-show-or-hide-compiler-links"></a>コンパイラ リンクの表示と非表示を切り替えるには  
  
1.  ソリューション エクスプ ローラーでマップを右クリックして、表示、およびをクリックするコンパイラ リンクを持つ**マップのテスト**です。  
  
2.  Visual Studio のエラー一覧 ウィンドウで、最後までスクロールしと表示されている行をダブルクリックして**コンパイラ リンクの表示/非表示には、ここをダブルクリックして**です。  
  
     この行をもう一度クリックすると、コンパイラ リンクの表示と非表示が切り替わります。  
  
    > [!NOTE]
    >  ときに、構築または再構築、BizTalk プロジェクトまたはソリューションの 1 つまたは複数のマップ、メッセージを含む**コンパイラ リンクの表示/非表示には、ここをダブルクリックして**に表示される、**エラー一覧**用の Visual Studio のウィンドウプロジェクトまたはソリューションのすべてのマップ。  
  
 マップをテストするには、入力インスタンスおよび出力インスタンスのプロパティを構成する必要があります。 これらのプロパティを構成する方法の詳細については、次を参照してください。[方法を構成するマップを検証およびテストのパラメーターに](../core/how-to-configure-map-validation-and-test-parameters.md)です。  
  
## <a name="see-also"></a>参照  
 [リンクを使用してレコードを指定してフィールドのマッピング](../core/using-links-to-specify-record-and-field-mappings.md)