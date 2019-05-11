---
title: BTAD_SilentMode |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BTAD_SilentMode [environment variable], about BTAS_SilentMode
- BTAD_SilentMode [environment variable]
- BTAD_SilentMode [environment variable], warnings
ms.assetid: 271835cf-1587-44c5-b5af-b4df4e981ab4
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9433dde06cf40b0c7c94091f48af4f4b37f9bdf2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357811"
---
# <a name="btadsilentmode"></a>BTAD_SilentMode
BTAD_SilentMode は、サイレント モードでスクリプトを実行するためのオプションを指定します。  
  
## <a name="remarks"></a>コメント  
 サイレント モードのオプションを指定するときに BTS インストーラーはその値を BTAD_SilentMode 変数に配置します。  
  
 BTAD_SilentMode の既定値は、2、サイレント モードで実行するスクリプトを指定します。 次の表では、BTAD_SilentMode の使用可能な値について説明します。  
  
> [!CAUTION]
>  スクリプトから BizTalk Server のユーザー インターフェイスを起動する場合のモーダル ダイアログ ボックス可能性がありますいないを表示するまたはが困難に表示および消去したり、フォーカスがあります。 BizTalk データベースはモーダル ダイアログ ボックスが開いている間ロックされ、アクセス不可能になります。 このため、実稼働システムでは、すべてのスクリプトはサイレント モードで実行する必要があります。  
  
|値|Description|  
|-----------|-----------------|  
|0|ユーザー インターフェイス (UI) のレベルは変更されません。|  
|1|既定の UI レベルを使用します。|  
|2|(既定値) のサイレント インストールを実行します。|  
|3|単純な進行状況とエラー処理を提供します。|  
|4|作成した UI を提供します。ウィザードを抑制します。|  
|0x80|上記の値と組み合わせると、スクリプトが正常に実行された場合、またはエラーがあった場合、Windows インストーラーはモーダル ダイアログ ボックスを表示します。 ユーザーが操作を取り消した場合、ダイアログ ボックスは表示されません。|  
|0x40|3 つの値と組み合わせると、Windows インストーラーは進行状況 ダイアログ ボックスが表示されますが、モーダル ダイアログ ボックスまたはエラー ダイアログ ボックスは表示されません。|  
|0x20|3 つの値と組み合わせると、Windows インストーラーは進行状況 ダイアログ ボックスが表示されますが、モーダル ダイアログ ボックスまたはエラー ダイアログ ボックスは表示されません。|  
|0x100|3 つの値と組み合わせると、Windows インストーラーは進行状況 ダイアログ ボックスが表示されますが、モーダル ダイアログ ボックスまたはエラー ダイアログ ボックスは表示されません。|  
  
## <a name="see-also"></a>参照  
 [前処理および後処理のスクリプト環境変数](../core/pre-and-post-processing-script-environment-variables.md)   
 [環境変数と展開状態の対応関係](../core/how-environment-variables-indicate-deployment-state.md)