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
ms.openlocfilehash: 2d21baa6ef6e6d82fc179497b4993cf3af6fb1a5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983987"
---
# <a name="how-environment-variables-indicate-deployment-state"></a>環境変数と展開状態の対応関係
処理前または処理後のスクリプトを呼び出すと、これらのスクリプトでは環境変数 BTAD_ChangeRequestAction、BTAD_InstallMode、および BTAD_HostClass を確認することにより、実行中の展開の状態 (インストール、インポート、削除、アンインストール、インポート ロールバック、インストール ロールバック) が判断されます。  

 次の表に、これら 3 つの環境変数の組み合わせとそれに対応する展開状態を示します。  


|       展開状態        |     予期される値      |
|-------------------------------|--------------------------|
|                               | BTAD_ChangeRequestAction |
| インポート (フラグの上書きなし) |          作成          |
|  インポート (フラグの上書きあり)   |          更新          |
|            インストール            |          更新          |
|           Uninstall           |          DELETE          |
|        インポート ロールバック        |          DELETE          |
|       インストール ロールバック        |          DELETE          |

## <a name="see-also"></a>参照  
 [前処理および後処理のスクリプトを使用したアプリケーション展開のカスタマイズ](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)   
 [BTAD_ChangeRequestAction](../core/btad-changerequestaction.md)   
 [BTAD_InstallMode](../core/btad-installmode.md)   
 [BTAD_HostClass](../core/btad-hostclass.md)