---
title: BTAD_SilentMode |Microsoft ドキュメント
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
ms.openlocfilehash: 31715835c98d2f60a3b5f1c18251571ea57641d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231330"
---
# <a name="btadsilentmode"></a>BTAD_SilentMode
BTAD_SilentMode は、スクリプトをサイレント モードで実行するためのオプションを指定します。  
  
## <a name="remarks"></a>解説  
 サイレント モードのオプションを指定すると、BTS インストーラーはその値を BTAD_SilentMode 変数に設定します。  
  
 BTAD_SilentMode の既定値は 2 で、スクリプトをサイレント モードで実行することを指定します。 BTAD_SilentMode で使用できる値を次の表に示します。  
  
> [!CAUTION]
>  スクリプトから BizTalk Server のユーザー インターフェイスを開始すると、モーダル ダイアログ ボックスが表示されない場合やフォーカスがない場合があり、表示や終了が困難になることがあります。 BizTalk データベースになり、ロックされたアクセスできないモーダル ダイアログ ボックスが開いている間です。 このため、実稼働システムでは、すべてのスクリプトをサイレント モードで実行する必要があります。  
  
|値|説明|  
|-----------|-----------------|  
|0|ユーザー インターフェイス (UI) のレベルを変更しません。|  
|1|既定の UI レベルを使用します。|  
|2|サイレント インストールを実行します (既定値)。|  
|3|簡単な進行状況とエラーの処理を提供します。|  
|4|作成した UI を提供し、ウィザードを起動しないようにします。|  
|0x80|前の値のいずれかと組み合わせると、Windows インストーラーは、スクリプトが正常に実行した場合、またはエラーが発生した場合に、モーダル ダイアログ ボックスを表示します。 ユーザーが操作を取り消した場合は、ダイアログ ボックスは表示されません。|  
|0x40|値 3 と組み合わせると、Windows インストーラーは、進行状況ダイアログ ボックスは表示しますが、モーダル ダイアログ ボックスまたはエラー ダイアログ ボックスは表示しません。|  
|0x20|値 3 と組み合わせると、Windows インストーラーは、進行状況ダイアログ ボックスは表示しますが、モーダル ダイアログ ボックスまたはエラー ダイアログ ボックスは表示しません。|  
|0x100|値 3 と組み合わせると、Windows インストーラーは、進行状況ダイアログ ボックスは表示しますが、モーダル ダイアログ ボックスまたはエラー ダイアログ ボックスは表示しません。|  
  
## <a name="see-also"></a>参照  
 [前処理および後処理のスクリプト環境変数](../core/pre-and-post-processing-script-environment-variables.md)   
 [環境変数が展開の状態を指定する方法](../core/how-environment-variables-indicate-deployment-state.md)