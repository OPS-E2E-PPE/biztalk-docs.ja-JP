---
title: "PIP 仕様を使用して、プロセス構成を作成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- PIPs, PIP settings
- PIPs, PIP secifications
- process configuration, PIPs
- PIPs, process configuration
ms.assetid: 64f0f5fb-f880-4ef1-95d7-2575b8d0bcff
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 777f32e5a9e035f6009f5450eb48ae8286159f05
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-pip-specification-to-create-a-process-configuration"></a>PIP 仕様を使用して、プロセス構成を作成するには
ダウンロードした後、プロセス PIP (Partner Interface)、RosettaNet 組織 (RosettaNet.org) から、ダウンロード パッケージには、PIP 仕様ドキュメントが含まれています。 このドキュメントには、[!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] 管理コンソールでプロセス構成を作成する場合に使用する設定についてのガイダンスが記載されています。  
  
## <a name="how-pip-settings-map-to-the-pip-specification"></a>PIP 設定と PIP 仕様の対応関係  
 次の表に、PIP 設定と RosettaNet PIP 仕様の情報の対応関係を示します。  
  
|プロセス構成設定|PIP 仕様の情報|  
|-----------------------------------|------------------------------------------|  
|[プロセス コード]|たとえば「PIP3A4」など、タイトル ページの小見出し|  
|バージョン|たとえば「02.02.00」など、タイトル ページの PIP バージョン識別子の小見出し|  
|[処理名]|たとえば「発注要求」など、タイトル ページの小見出し|  
|[説明] ([全般] タブ)|セクション 3.1、ビジネス プロセス定義|  
|[否認不可の必要性]|表 3-3: ビジネス アクティビティ パフォーマンス コントロール|  
|時間 (秒) を確認するには|表 3-3: ビジネス アクティビティ パフォーマンス コントロール|  
|[認証の必要性]|表 3-3: ビジネス アクティビティ パフォーマンス コントロール|  
|[永続的な機密性の必要性]|(PIP 仕様からの参照なし)|  
|[セキュリティで保護されたトランスポートの必要性]|表 4-3: メッセージ交換コントロール|  
|[シングル アクション]|セクション 4.3、取り引きダイアログ仕様|  
|[発信元とコンテンツの否認不可]|表 3-3: ビジネス アクティビティ パフォーマンス コントロール|  
|再試行の回数|表 3-3: ビジネス アクティビティ パフォーマンス コントロール|  
|[実行までの時間]|表 3-3: ビジネス アクティビティ パフォーマンス コントロール|  
|名前|表 3-3: ビジネス アクティビティ パフォーマンス コントロール (アクティビティ名)|  
|型|(PIP 仕様からの参照なし - 将来使用予定)|  
|[説明] ([開始側] タブと [応答側] タブ)|表 3-4: PIP ビジネス ドキュメント|  
|[名前] ([開始側] タブと [応答側] タブ)|表 3-4: PIP ビジネス ドキュメント|  
|[ロール] ([開始側] タブと [応答側] タブ)|表 3-1: パートナーのロールの説明|  
|[ロールの説明] ([開始側] タブと [応答側] タブ)|表 3-1: パートナーのロールの説明|  
|[ロールの種類] ([開始側] タブと [応答側] タブ)|表 3-1: パートナーのロールの説明|  
|サービス|表 4-1: ネットワーク コンポーネントの仕様|  
|[サービスの分類]|表 4-1: ネットワーク コンポーネントの仕様|  
  
## <a name="see-also"></a>参照  
 [作成またはプロセス構成を編集する方法](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)