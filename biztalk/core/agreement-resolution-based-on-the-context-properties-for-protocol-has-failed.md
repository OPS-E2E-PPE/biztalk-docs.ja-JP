---
title: アグリーメントの解決は、プロトコルが失敗しましたコンテキスト プロパティに基づく |。Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58fccd84-579c-4b5e-872b-33730d4079e8
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76d74ad7aa4a73f4a0befcef32bc8051195cb080
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22229938"
---
# <a name="agreement-resolution-based-on-the-context-properties-for-protocol-has-failed"></a>プロトコルに対するコンテキスト プロパティに基づくアグリーメントの解決が失敗しました
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|AgreementResolutionContextPropertiesLookupFailed|  
|メッセージ テキスト|アグリーメントの解決は、プロトコルが失敗した {0} のコンテキスト プロパティに基づいています。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、BizTalk Server がユーザーによって指定されたコンテキスト プロパティに基づいてアグリーメントを解決できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、アグリーメントの解決が実行されるように、BizTalk メッセージの一部としてコンテキスト プロパティを指定します。