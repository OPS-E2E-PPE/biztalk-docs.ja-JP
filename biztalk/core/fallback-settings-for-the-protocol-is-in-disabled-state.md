---
title: "プロトコルに対するフォールバック設定が無効状態です |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f14a5e46-1028-4250-af7b-8137fa927d7e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9060dbe2bf3644310d862d4949d2cf944269105d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# プロトコルに対するフォールバック設定が無効状態です
## 詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|AgreementResolutionFallbackSettingsDisabled|  
|メッセージ テキスト|{0} プロトコルに対するフォールバック設定が無効状態です。|  
  
## 説明  
 このエラー/警告/情報イベントは、BizTalk Server がアグリーメントに解決でき、フォールバック設定にリダイレクトされたが、特定のプロトコルに対するフォールバック設定が無効な状態だったことを示します。  
  
## ユーザーの操作  
 このエラーを解決するのには、特定のプロトコルに対するフォールバック設定を有効にしてください。