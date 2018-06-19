---
title: ネットワークのパフォーマンスの最適化 |Microsoft ドキュメント
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
ms.openlocfilehash: 8225bd082140ac1347bc99a91ea209f9d79a8bab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299050"
---
# <a name="optimizing-network-performance"></a>ネットワーク パフォーマンスを最適化します。
BizTalk Server コンピューターが SQL Server コンピューターとは別の場所、BizTalk Server 環境で BizTalk Server によって処理される各メッセージには、ネットワーク経由で通信が必要です。 この通信には、BizTalk Server コンピューターと BizTalk メッセージ ボックス データベース、BizTalk 管理データベース、BAM データベースおよびその他のデータベース間のかなりのトラフィックが含まれています。 高負荷のシナリオで、この通信は大量のネットワーク トラフィックにより、ネットワーク設定が最適化されていない、十分なネットワーク インターフェイス カードがインストールされている、または十分なネットワーク帯域幅が場合は特に、ボトルネックになることができます。使用できます。  
  
 このセクションでは、ネットワークのパフォーマンスを向上させるための一般的な推奨事項を説明し、ネットワーク上のボトルネックの発生を軽減するために、ネットワーク スタックを最適化するために変更できるいくつかのレジストリ エントリについて説明します。  
  
> [!IMPORTANT]  
>  このセクションの推奨事項の一部には、Windows レジストリに対する変更が必要があります。 レジストリ エディターの不適切な使用により問題が発生し、オペレーティング システムの再インストールが必要となることがあります。 レジストリ エディターは、ご自身の責任で使用してください。 バックアップ、復元、およびレジストリを変更する方法の詳細については、Microsoft サポート技術情報の記事を参照してください。 [256896、"Windows のレジストリ情報上級ユーザー向けに"](http://go.microsoft.com/fwlink/?LinkId=62729) (http://go.microsoft.com/fwlink/?LinkId=62729)。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ネットワークのパフォーマンスを向上させるための一般的なガイドライン](../technical-guides/general-guidelines-for-improving-network-performance.md)  
  
-   [ネットワーク パフォーマンスを向上するように変更する設定](../technical-guides/settings-that-can-be-modified-to-improve-network-performance.md)  
  
## <a name="see-also"></a>参照  
 [パフォーマンスを最適化します。](../technical-guides/optimizing-performance.md)