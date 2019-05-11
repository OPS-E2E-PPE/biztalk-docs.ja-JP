---
title: プロトコルに対するフォールバック設定が無効状態です |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f14a5e46-1028-4250-af7b-8137fa927d7e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bcdf55fba8a8a83f0bf6cc6126707caffe5d0694
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345854"
---
# <a name="fallback-settings-for-the-protocol-is-in-disabled-state"></a>プロトコルに対するフォールバック設定が無効状態です。
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                      AgreementResolutionFallbackSettingsDisabled                       |
|  メッセージ テキスト   |              に対するフォールバック設定が、{0}プロトコルが無効状態です。              |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、BizTalk Server がアグリーメントに解決できがされているフォールバックの設定にリダイレクトおよびフォールバックの設定は、特定のプロトコルの無効の状態があったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するのには、特定のプロトコルに対するフォールバック設定を有効にしてください。