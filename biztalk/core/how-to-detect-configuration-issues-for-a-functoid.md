---
title: Functoid の構成の問題を検出する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 32afc333-934c-4ffb-b1b5-61af07157200
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8561156091c992e9329ef7d9627589eff9e0ed6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968968"
---
# <a name="how-to-detect-configuration-issues-for-a-functoid"></a>Functoid の構成に関する問題を検出する方法
マップを操作しているときに、Functoid やリンクの構成に関する問題が発生する可能性があります。 BizTalk マッパーでは、ビジュアル化機構を使用して、functoid の構成に関連する問題をすばやく識別できます。 この視覚的で、functoid アイコンで警告の注釈として表示されます (の例: ![Functoid IntelliSense](../core/media/mapper-functoidintellisense.gif "Mapper_FunctoidIntelliSense"))、リレーションシップ ビューでします。 このトピックでは、Functoid の構成の問題を検出する方法について説明します。  
  
 警告状態アイコンは、Functoid が適切に構成されていないことをマッパーが検出した場合に表示されます。 Functoid 上にマウスを移動すると、マッパーによって検出された問題の簡単な説明が表示されます。 たとえば、Functoid に最小数の有効な入力がない場合、Functoid のツールヒントに必要な入力パラメーターの数が示されます。  
  
## <a name="prerequisites"></a>前提条件  
 この操作では、BizTalk マッパーが実行されている必要があります。  
  
### <a name="to-detect-configuration-issues-for-a-functoid"></a>Functoid の構成の問題を検出するには  
  
1.  必要な Functoid をツールボックスからグリッド ページにドラッグします。 Functoid に警告アイコンが表示されます。  
  
2.  次のいずれかの操作が可能です。  
  
    -   マウス ポインターを Functoid 上に移動します。 ツールヒントに、エラーと対処方法に関する情報が表示されます。  
  
         次の図は、Functoid "Addition" の構成時のエラー情報が表示されたツールヒントです。  
  
         ![Functoid の構成のエラー検出](../core/media/errordetectionfunctoid.gif "ErrorDetectionFunctoid")  
  
    -   Functoid をダブルクリックします。 **構成\<Functoid\> Functoid**  ダイアログ ボックスには、入力パラメーターの警告アイコンが表示されます。 これは、選択した Functoid の入力パラメーターが構成されていないことを示します。  
  
         次の図は、"Addition" Functoid の入力パラメーターに関するエラー情報を示しています。  
  
         ![Functoid が構成されていないときに表示される警告](../core/media/configure-input-parameters-warningicon.gif "Configure_input_parameters_WarningIcon")  
  
## <a name="see-also"></a>参照  
 [BizTalk マッパーの強化された機能の使用](../core/using-enhanced-features-in-biztalk-mapper.md)