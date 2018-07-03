---
title: 'シングル サインオン: イベント 11026 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e39b252d-2ed0-4006-aac2-4dce6504afb2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 452ccc24174a1e32a133c0ccc6c7a0b5f09c530f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013491"
---
# <a name="single-sign-on-event-11026"></a>シングル サインオン: イベント 11026
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                エンタープライズ シングル サインオン                                                                                                                                |
| 製品バージョン |                                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                |
|    イベント ID     |                                                                                                                                          11026                                                                                                                                          |
|  イベント ソース   |                                                                                                                                         ENTSSO                                                                                                                                          |
|    コンポーネント    |                                                                                                                                           なし                                                                                                                                           |
|  シンボル名  |                                                                                                                             SSO_WARN_EXISTING_GROUP_MAPPING                                                                                                                             |
|  メッセージ テキスト   | 既存のマッピングとの競合があるため、新しいグループ マッピングを作成できませんでした。 既存のマッピングを削除してから、再度実行してください。%r<br /><br /> 既存のマッピング: % 1 %r<br /><br /> 新しいマッピング: % 2 %r<br /><br /> 外部アカウント: % 3 %r<br /><br /> アプリケーション名: %4 |
  
## <a name="explanation"></a>説明  
 最も可能性が高い原因は、システムが古いバージョンのエンタープライズ シングル サインオンと古いグループ アプリケーションを使用していることです。  
  
## <a name="user-action"></a>ユーザーの操作  
 警告で指摘されているように、マッピングを削除して作成しなおします。 これが失敗する場合は、より新しいバージョンのエンタープライズ シングル サインオンにアップグレードすることが必要な可能性があります。