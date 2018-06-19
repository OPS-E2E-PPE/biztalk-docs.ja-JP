---
title: 除外条件の違反 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e508da6-7edc-45c0-a7ab-f23337dc1b54
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5a508c113daf628491837adee119649ac17b478
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245962"
---
# <a name="exclusion-condition-violated"></a>除外条件に違反しました
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|X12DeExclusionConditionViolatedDescription|  
|メッセージ テキスト|除外条件に違反しました。詳細については、インスタンスのフィールドの値を参照してください。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、デザイン時 (XML 検証ツール使用時) または実行時に、インスタンス内のセグメントがクロスフィールド検証の除外ルールに違反したため、受信側または送信側のいずれかで X12 インターチェンジの検証が失敗したことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、除外ルールに違反したセグメントがクロスフィールド検証を通過するように変更されたことを確認し、検証プロセスを再度実行します。