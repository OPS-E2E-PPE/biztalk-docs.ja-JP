---
title: EDI パーティに関する既知の問題 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 86475960-cdb2-4b39-817a-b5d834f498a9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fddda6dd62e8e3bd2d38574343b7fcb0e0d76f89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261786"
---
# <a name="known-issues-with-edi-parties"></a>EDI パーティに関する既知の問題
このセクションには、EDI パーティと、パートナー アグリーメント マネージャに関する既知の問題を説明するトピックが含まれています。  
  
## <a name="a-cache-refresh-period-delays-availability-of-a-changed-party-property"></a>キャッシュ更新間隔による変更後のパーティ プロパティの使用可能時期の遅延  
 PAM でパーティまたはグローバル プロパティを変更すると、15 分ごとのキャッシュ更新または BizTalk サービスの再起動の後に、BizTalk Runtime でそのプロパティが使用可能になります。  
  
## <a name="see-also"></a>参照  
 [EDI 受信確認を構成します。](../core/configuring-edi-acknowledgments.md)   
 [EDI 処理におけるアグリーメントのロール](../core/the-role-of-agreements-in-edi-processing.md)   
 [EDI のプロパティを構成します。](../core/configuring-edi-properties.md)   
 [グローバルまたはフォールバック アグリーメント プロパティの構成](../core/configuring-global-or-fallback-agreement-properties.md)