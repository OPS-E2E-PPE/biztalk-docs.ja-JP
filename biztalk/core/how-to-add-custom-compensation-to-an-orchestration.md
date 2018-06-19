---
title: カスタム補正をオーケストレーションに追加する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 3eadb9cba6e5a49be516a8095b01f93ca7a490f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248122"
---
# <a name="how-to-add-custom-compensation-to-an-orchestration"></a>カスタム補正をオーケストレーションに追加する方法
長時間トランザクションとして構成されたオーケストレーションのトランザクションにはカスタム補正コードを記述し、トランザクションの効果を取り消したり、元に戻したりできます。 呼び出し元のオーケストレーションの補正ブロックを使用して呼び出すことができます、オーケストレーションが正常に完了したが、別のオーケストレーションによって呼び出された場合は、**補正**図形です。  
  
### <a name="to-specify-that-an-orchestration-will-use-custom-compensation"></a>オーケストレーションがカスタム補正を使用するように指定するには  
  
1.  オーケストレーションの種類 ウィンドウで、選択**オーケストレーションのプロパティ**です。  
  
2.  [プロパティ] ウィンドウで選択**カスタム**のドロップダウン リストで、**補正**プロパティです。  
  
     **補正** タブが横に表示、**オーケストレーション**デザイン画面の下部にあるタブ。  
  
### <a name="to-design-custom-compensation-for-an-orchestration"></a>オーケストレーションのカスタム補正をデザインするには  
  
1.  クリックして、**補正**デザイン画面の下部にあるタブ。  
  
     **補正デザイン サーフェイス**が表示されます。  
  
2.  図形を追加、**補正デザイン サーフェイス**の場合と同様、**オーケストレーション デザイン画面**です。  
  
     詳細については、次を参照してください。[オーケストレーションに図形を追加する](../core/how-to-add-shapes-to-orchestrations.md)です。  
  
## <a name="see-also"></a>参照  
 [トランザクション オーケストレーションを行う](../core/making-orchestrations-transactional.md)