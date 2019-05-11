---
title: 環境変数が展開の状態を指定する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- scripts, variables
ms.assetid: 022b782b-008d-41a7-9880-d1c4e5e4015e
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fc27a85f36b83b3fd3c0bd782807fa4f5b73364
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387461"
---
# <a name="how-environment-variables-indicate-deployment-state"></a>環境変数と展開状態の対応関係
展開の状態の前または処理後のスクリプトを調べる、呼び出されると (インストール、インポート、削除、アンインストール、インポート ロールバック、またはインストール ロールバック) により、環境変数 BTAD_ChangeRequestAction、BTAD_InstallMode、実行中におよび BTAD_HostClass を選択します。  

 次の表では、さまざまな展開の状態を示す 3 つの変数の組み合わせについて説明します。  


|       展開状態        |     予期される値      |
|-------------------------------|--------------------------|
|                               | BTAD_ChangeRequestAction |
| インポート フラグの上書きなし |          作成          |
|  上書きフラグにインポートする.   |          更新          |
|            インストール            |          更新          |
|           アンインストール           |          DELETE          |
|        インポート ロールバック        |          DELETE          |
|       インストール ロールバック        |          DELETE          |

## <a name="see-also"></a>参照  
 [前処理および後処理のスクリプトを使用したアプリケーション展開のカスタマイズ](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)   
 [BTAD_ChangeRequestAction](../core/btad-changerequestaction.md)   
 [BTAD_InstallMode](../core/btad-installmode.md)   
 [BTAD_HostClass](../core/btad-hostclass.md)