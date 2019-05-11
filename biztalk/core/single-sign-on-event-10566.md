---
title: シングル サインオン:イベント 10566 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7bd140b-5503-40f8-bf5d-604fa763989e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27530a47a1262cbc5baf9edede91dcee385fa91e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398786"
---
# <a name="single-sign-on-event-10566"></a>シングル サインオン:イベント 10566
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                     エンタープライズ シングル サインオン                                                                      |
| 製品バージョン |                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                     |
|    イベント ID     |                                                                               10566                                                                                |
|  イベント ソース   |                                                                               ENTSSO                                                                               |
|    コンポーネント    |                                                                                なし                                                                                 |
|  シンボル名  |                                                                  SSO_WARN_CANNOT_UPDATE_APP_FLAGS                                                                  |
|  メッセージ テキスト   | このアプリケーションの指定したフラグの一部を更新することはできません。 Ignored.%r されます。<br /><br /> アプリケーション名: %1 %r<br /><br /> 指定フラグ マスク: %2 |
  
## <a name="explanation"></a>説明  
 アプリケーションの特定のフラグを変更することはできません。 (たとえば、ことはできませんをグループに個々 のアプリケーションの種類を変更する。)このアプリケーションのフラグは、警告テキストで指定されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 ユーザーによる操作は不要です。