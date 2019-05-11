---
title: Functoid の構成の問題を検出する方法 |Microsoft Docs
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
ms.openlocfilehash: da91fbeb9afc3d6f93a319e82e7e83d396ad4e16
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385233"
---
# <a name="how-to-detect-configuration-issues-for-a-functoid"></a>Functoid の構成に関する問題を検出する方法
マップを操作しているときに、functoid やリンクの構成に関する問題が発生する可能性があります。 BizTalk マッパーでは、視覚化メカニズムを使用して、functoid の構成に関連する問題をすばやく識別できます。 この視覚的で、functoid アイコンで警告の注釈として表示されます (の例: ![Functoid IntelliSense](../core/media/mapper-functoidintellisense.gif "Mapper_FunctoidIntelliSense"))、リレーションシップ ビューで。 このトピックでは、functoid の構成の問題を検出する方法についての情報を提供します。  
  
 マッパー functoid が正しく構成されていないことを検出すると、警告状態アイコンが表示されます。 Functoid 上にマウスを動かすと、マッパーによって特定された問題の簡単な情報も表示されます。 たとえば、functoid が有効な入力値の最小数を持たない場合、functoid のツールヒントは、必要な入力パラメーターの数を示しています。  
  
## <a name="prerequisites"></a>前提条件  
 この操作では、BizTalk マッパーが実行されている必要があります。  
  
### <a name="to-detect-configuration-issues-for-a-functoid"></a>Functoid の構成の問題を検出するには  
  
1.  ツールボックスからグリッド ページに必要な functoid をドラッグします。 警告アイコンが functoid が表示されます。  
  
2.  次のいずれかの操作を行うことができます。  
  
    -   Functoid には、マウス ポインターを移動します。 ツールヒントには、行う必要があるとエラーに関する情報が表示されます。  
  
         次の図は、functoid"Addition。"を構成するときにエラー情報を含むヒントを表示します。  
  
         ![Functoid の構成でのエラー検出](../core/media/errordetectionfunctoid.gif "ErrorDetectionFunctoid")  
  
    -   Functoid をダブルクリックします。 **構成\<Functoid\> Functoid**  ダイアログ ボックスに入力パラメーターの警告アイコンが表示されます。 これは、選択した functoid の入力パラメーターが構成されていないことを示します。  
  
         次の図は、"Addition"functoid の入力パラメーターに関するエラー情報を表示します。  
  
         ![Functoid が構成されていないときに表示される警告](../core/media/configure-input-parameters-warningicon.gif "Configure_input_parameters_WarningIcon")  
  
## <a name="see-also"></a>参照  
 [BizTalk マッパーの強化された機能の使用](../core/using-enhanced-features-in-biztalk-mapper.md)