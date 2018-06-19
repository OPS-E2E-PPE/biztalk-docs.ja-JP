---
title: EDI および AS2 のパフォーマンスに関する既知の問題 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c47294f9-f728-4b6b-abe1-578434eb54df
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e034cf228ee92157c4b29c36660111bb1856c358
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261762"
---
# <a name="known-issues-with-edi-and-as2-performance"></a>EDI および AS2 のパフォーマンスに関する既知の問題
このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI ソリューションおよび AS2 ソリューションのパフォーマンスに関する既知の問題について説明します。  
  
## <a name="performance-considerations-for-edi-and-as2-status-reporting"></a>EDI および AS2 状態レポートのパフォーマンスに関する考慮事項  
 EDI または AS2 状態レポートを有効にすると、状態レポートが実行される対象のメッセージの数によってはシステムのパフォーマンスに影響が及ぶ場合があります。 EDI または AS2 の処理に "レポート用にトランザクション セット/ペイロードを格納する" プロパティを選択すると、状態レポートが実行される対象のメッセージのサイズによってはシステムのパフォーマンスに影響が及ぶことがあります。  
  
 EDI または AS2 状態レポート用に BAMPrimaryImport データベースで使用されるテーブルは、最適化されています。 さらに最適化を行う必要はありません。 ただし、BAMPrimaryImport データベースに格納されているアクティビティ インスタンス データをアーカイブする時間枠を変更することで、BAM プライマリ インポート データベースのデータがアーカイブされる速度を高めることができます。 詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] マニュアルの「プライマリ インポート データベースのデータのアーカイブ」を参照してください。  
  
 トランザクション セット/ペイロード データは、BizTalkDTADb データベースに格納されます。 このデータベースのパフォーマンスの詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] マニュアルの「DTA 追跡のパフォーマンス特性について」を参照してください。  
  
 システムのパフォーマンスは、システムの構成で有効に設定されている状態レポートのレベルによって影響を受けることもあります。 特定の種類の状態レポートを無効にすることによってパフォーマンスを向上させることも可能です。  
  
## <a name="see-also"></a>参照  
 [EDI および AS2 ソリューションのトラブルシューティング](../core/troubleshooting-edi-and-as2-solutions.md)