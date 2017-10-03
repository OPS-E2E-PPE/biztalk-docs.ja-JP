---
title: "環境変数が展開の状態を指定する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: scripts, variables
ms.assetid: 022b782b-008d-41a7-9880-d1c4e5e4015e
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 041e77eadb7c1b62e3441ee3b3c138203299f3a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-environment-variables-indicate-deployment-state"></a>環境変数と展開状態の対応関係
処理前または処理後のスクリプトを呼び出すと、これらのスクリプトでは環境変数 BTAD_ChangeRequestAction、BTAD_InstallMode、および BTAD_HostClass を確認することにより、実行中の展開の状態 (インストール、インポート、削除、アンインストール、インポート ロールバック、インストール ロールバック) が判断されます。  
  
 次の表に、これら 3 つの環境変数の組み合わせとそれに対応する展開状態を示します。  
  
|展開状態|予期される値|  
|----------------------|---------------------|  
||BTAD_ChangeRequestAction|BTAD_InstallMode|BTAD_HostClass|  
|インポート (フラグの上書きなし)|作成|[インポート]|ConfigurationDb|  
|インポート (フラグの上書きあり)|Update|[インポート]|ConfigurationDb|  
|Install|Update|Install|BizTalkHostInstance|  
|Uninstall|DELETE|Uninstall|BizTalkHostInstance|  
|インポート ロールバック|DELETE|[インポート]|ConfigurationDb|  
|インストール ロールバック|DELETE|Install|BizTalkHostInstance|  
  
## <a name="see-also"></a>参照  
 [前処理および後処理のスクリプトを使用したアプリケーションの展開のカスタマイズ](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)   
 [BTAD_ChangeRequestAction](../core/btad-changerequestaction.md)   
 [BTAD_InstallMode](../core/btad-installmode.md)   
 [BTAD_HostClass](../core/btad-hostclass.md)