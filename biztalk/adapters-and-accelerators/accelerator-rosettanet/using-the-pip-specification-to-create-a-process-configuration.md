---
title: PIP 仕様を使用して、プロセス構成を作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PIPs, PIP settings
- PIPs, PIP secifications
- process configuration, PIPs
- PIPs, process configuration
ms.assetid: 64f0f5fb-f880-4ef1-95d7-2575b8d0bcff
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21933797f37b32a4131c57181829f2380bafe061
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299920"
---
# <a name="using-the-pip-specification-to-create-a-process-configuration"></a>PIP 仕様を使用して、プロセス構成を作成するには
RosettaNet 組織 (RosettaNet.org) から、プロセス PIP (Partner Interface) をダウンロードした後、ダウンロード パッケージには、PIP 仕様のドキュメントが含まれています。 このドキュメントにはでプロセス構成を作成するときに使用するには、どのような設定に関するガイダンスが含まれています、[!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]管理コンソール。  
  
## <a name="how-pip-settings-map-to-the-pip-specification"></a>PIP の PIP 仕様にマップを設定する方法  
 次の表では、PIP 設定が RosettaNet PIP 仕様の情報にマップする方法について説明します。  
  
|プロセス構成設定|PIP 仕様の情報|  
|-----------------------------------|------------------------------------------|  
|プロセス コード|たとえば、「pip3a4」など、タイトル ページの小見出し|  
|バージョン|[タイトル] ページで、たとえば「02.02.00」などの PIP バージョン識別子の小見出し|  
|[処理名]|たとえば、発注要求"、タイトル ページの小見出し|  
|[説明] \([全般] タブ)|セクション 3.1、ビジネス プロセスの定義|  
|否認不可が必要|表 3-3:ビジネス アクティビティ パフォーマンス コントロール|  
|時間 (秒) を確認するには|表 3-3:ビジネス アクティビティ パフォーマンス コントロール|  
|承認が必要ですか。|表 3-3:ビジネス アクティビティ パフォーマンス コントロール|  
|永続的な機密性の必要性は、します。|(PIP 仕様から参照なし)|  
|セキュリティで保護されたトランスポートのために必要なのですか。|表 4-3:メッセージ交換コントロール|  
|シングル アクションします。|セクション 4.3、取り引きダイアログ仕様|  
|[発信元とコンテンツの否認不可]|表 3-3:ビジネス アクティビティ パフォーマンス コントロール|  
|再試行の回数|表 3-3:ビジネス アクティビティ パフォーマンス コントロール|  
|実行する時間|表 3-3:ビジネス アクティビティ パフォーマンス コントロール|  
|名前|表 3-3:ビジネス アクティビティ パフォーマンス コントロール (アクティビティ名)|  
|型|(将来使用するために、PIP 仕様から参照なし)|  
|[説明] \([開始側] タブと [応答側] タブ)|表 3-4:PIP ビジネス ドキュメント|  
|[名前] \([開始側] タブと [応答側] タブ)|表 3-4:PIP ビジネス ドキュメント|  
|[ロール] \([開始側] タブと [応答側] タブ)|表 3-1:パートナーのロールの説明|  
|[ロールの説明] \([開始側] タブと [応答側] タブ)|表 3-1:パートナーのロールの説明|  
|[ロールの種類] \([開始側] タブと [応答側] タブ)|表 3-1:パートナーのロールの説明|  
|サービス|表 4-1:ネットワーク コンポーネントの仕様|  
|サービスの分類|表 4-1:ネットワーク コンポーネントの仕様|  
  
## <a name="see-also"></a>参照  
 [プロセス構成を作成または編集する方法](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)