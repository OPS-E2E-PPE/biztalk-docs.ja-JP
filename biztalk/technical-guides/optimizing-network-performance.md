---
title: ネットワーク パフォーマンスの最適化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b6c3985a-48b3-489b-8fe3-3b7bfd0515f9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30d58dcac30f2f2395aa9407aaf18fd039c3458f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291377"
---
# <a name="optimizing-network-performance"></a>ネットワーク パフォーマンスを最適化します。
BizTalk Server コンピューターが SQL Server コンピューターとは別の BizTalk Server 環境で BizTalk Server によって処理される各メッセージには、ネットワーク経由で通信が必要です。 この通信には、BizTalk Server コンピューターと BizTalk メッセージ ボックス データベース、BizTalk 管理データベース、BAM データベース、およびその他のデータベース間のかなりのトラフィックが含まれています。 高負荷のシナリオでこの通信により、かなりのネットワーク トラフィックとネットワークの設定が最適化されていない、十分なネットワーク インターフェイス カードがインストールされている場合、または十分なネットワーク帯域幅が場合は特に、ボトルネックになることができます。ご利用いただけます。  
  
 このセクションでは、ネットワークのパフォーマンスを向上させるための一般的な推奨事項を提供し、ネットワーク上のボトルネックの発生を軽減するために、ネットワーク スタックを最適化するために変更可能ないくつかのレジストリ エントリについて説明します。  
  
> [!IMPORTANT]  
>  このセクションの推奨事項の一部には、Windows レジストリに対する変更が必要です。 レジストリ エディターの不適切な使用により問題が発生し、オペレーティング システムの再インストールが必要となることがあります。 レジストリ エディターは、ご自身の責任で使用してください。 バックアップ、復元、およびレジストリを変更する方法の詳細については、マイクロソフト サポート技術情報の記事を参照してください。 [256896、"Windows レジストリ情報の高度なユーザー"](http://go.microsoft.com/fwlink/?LinkId=62729) (http://go.microsoft.com/fwlink/?LinkId=62729)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ネットワークのパフォーマンスを向上するための一般的なガイドライン](../technical-guides/general-guidelines-for-improving-network-performance.md)  
  
-   [ネットワーク パフォーマンスを向上するために変更できる設定](../technical-guides/settings-that-can-be-modified-to-improve-network-performance.md)  
  
## <a name="see-also"></a>参照  
 [パフォーマンスの最適化](../technical-guides/optimizing-performance.md)