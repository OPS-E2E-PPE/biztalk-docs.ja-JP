---
title: 手順 3:定義する、発行、および Contoso のビジネス ポリシーの展開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, deploying
- policies, publishing
- private process tutorial, creating policies
- policies, creating
ms.assetid: 529b16d8-226b-4046-a95d-64162ebd59a3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d0b94deb38356325c81dd1b5192c726e75a43ff0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281099"
---
# <a name="step-3-defining-publishing-and-deploying-the-business-policy-for-contoso"></a>手順 3:定義する、発行、および Contoso のビジネス ポリシーを展開します。
ここでは、緊急時に使用するために、Contoso が製造する各製品を決められた数量だけ取っておくビジネス ポリシーを作成します。  
  
### <a name="to-add-a-new-policy"></a>新しいポリシーを追加するには  
  
1.  ポリシー エクスプローラ ペインで、ビジネス ルール作成ツールで右クリック**ポリシー**、クリックして**新しいポリシーの追加**です。  
  
2.  新しいポリシーの名前**3 a2priceavailabilitypolicy**、キーを押します**Enter**です。  
  
### <a name="to-add-a-policy-rule-to-enforce-the-emergency-quantity-needs"></a>緊急時の必要数量を決定するポリシー ルールを追加するには  
  
1.  右クリック**バージョン 1.0 (未保存)**  **3 a2priceavailabilitypolicy**、クリックして**新しいルールの追加**です。  
  
2.  ルールの名前として**Quantity Exhausted Emergency Supply Rule -**、キーを押します**Enter**です。  
  
3.  右側のウィンドウで、ビジネス ルール作成ツールで右クリック**条件**IF ペインで、をポイント**述語**、をクリックし、**以下**述語。  
  
4.  ファクト エクスプ ローラー ウィンドウで **ボキャブラリ**、展開**3 a2priceavailabilityvocabulary**、展開**バージョン 1.0 - 公開済み****数量使用可能な**、上にドラッグし、`argument1`作成ツール画面上のプレース ホルダーです。  
  
5.  手順 4 をドラッグして**Emergency Quantity Needed**上に、`argument2`プレース ホルダーです。  
  
6.  選択**Final Quantity Available**にドラッグ**アクション**[THEN] ペインでします。  
  
### <a name="to-add-a-policy-to-revise-the-number-available-field-in-the-response"></a>必要に応じて [Number Available] フィールドを修正するポリシーを追加するには  
  
1.  右クリック**バージョン 1.0 (未保存)**  **3 a2priceavailabilitypolicy**、クリックして**新しいルールの追加**です。  
  
2.  ルールの名前として**Emergency Supply Rule - Quantity Available**、キーを押します**Enter**です。  
  
3.  右側のウィンドウで、ビジネス ルール作成ツールで右クリック**条件**IF ペインで、をポイント**述語**、をクリックし、**より大きい**述語。  
  
4.  ファクト エクスプ ローラー ウィンドウで **ボキャブラリ**、展開**3 a2priceavailabilityvocabulary**、展開**バージョン 1.0 - 公開済み****数量使用可能な**、上にドラッグし、`argument1`作成ツール画面上のプレース ホルダーです。  
  
5.  ドラッグして、その同じ手順を繰り返します**Emergency Quantity Needed**上に、`argument2`プレース ホルダーです。  
  
6.  選択**Final Quantity Available**にドラッグ**アクション**[THEN] ペインでします。  
  
7.  ファクト エクスプ ローラー ウィンドウで **バージョン 1.0 - 公開済み****関数**、ドラッグ、`Subtract`関数、 **0**隣にある引数**Final Quantity Available** THEN ペインでします。  
  
8.  ドラッグ**Quantity Available** ( **3 a2priceavailabilityvocabulary**) にドロップし、 `value1` THEN ペイン内のプレース ホルダーです。  
  
9. ドラッグ**Emergency Quantity Needed**、上にドロップし、 `value2` [THEN] ペイン内のプレース ホルダーです。  
  
### <a name="to-save-publish-and-deploy-the-business-policy"></a>ビジネス ポリシーの保存、公開、展開を行うには  
  
1.  ポリシー エクスプローラ ペインで右クリック**バージョン 1.0 (未保存)**  **3 a2priceavailabilitypolicy**をクリックし、**保存**です。  
  
2.  その同じノードを右クリックし、をクリックして**発行**です。  
  
3.  その同じノードを右クリックし、をクリックして**展開**です。  
  
## <a name="see-also"></a>参照  
 [手順 4:HeaderHelper プロジェクトの作成](../../adapters-and-accelerators/accelerator-rosettanet/step-4-creating-the-headerhelper-project.md)