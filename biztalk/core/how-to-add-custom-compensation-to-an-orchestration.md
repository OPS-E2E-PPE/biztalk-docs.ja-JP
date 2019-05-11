---
title: カスタム補正をオーケストレーションに追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, compensations
- Compensate shape [Orchestration Designer]
- Compensate shape [Orchestration Designer], orchestrations
- Compensation property
- orchestrations, transactional
- orchestrations, customizing
- customizing, orchestrations
- Compensate shape [Orchestration Designer], custom compensation
ms.assetid: d153498d-8f98-42ae-90b9-e3083d669aef
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09c8d6bfa6f935c6d34de093fc066eee420705b7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343301"
---
# <a name="how-to-add-custom-compensation-to-an-orchestration"></a>カスタム補正をオーケストレーションに追加する方法
実行時間の長いとして構成されているオーケストレーション トランザクションには、カスタム補正コードを逆に、トランザクションの効果を元に戻すことができます。 補正ブロックを使用して呼び出し元のオーケストレーションを呼び出すことができます、オーケストレーションが正常に完了しましたが別のオーケストレーションによって呼び出された場合、**補正**図形。  
  
### <a name="to-specify-that-an-orchestration-will-use-custom-compensation"></a>オーケストレーションがカスタム補正を使用するように指定するには  
  
1.  オーケストレーションの種類 ウィンドウで次のように選択します。**オーケストレーションのプロパティ**します。  
  
2.  [プロパティ] ウィンドウで次のように選択します。**カスタム**のドロップダウン リストで、**補正**プロパティ。  
  
     **補正**タブが横に表示されます、**オーケストレーション**デザイン画面の下部にあるタブ。  
  
### <a name="to-design-custom-compensation-for-an-orchestration"></a>オーケストレーションのカスタム補正をデザインするには  
  
1.  をクリックして、**補正**デザイン画面の下部にあるタブ。  
  
     **補正デザイン サーフェイス**が表示されます。  
  
2.  図形を追加、**補正デザイン サーフェイス**の場合と同様、**オーケストレーション デザイン画面**します。  
  
     詳細については、次を参照してください。[オーケストレーションに図形を追加する](../core/how-to-add-shapes-to-orchestrations.md)します。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションのトランザクション化](../core/making-orchestrations-transactional.md)