---
title: 'シングル サインオン: イベント 10665 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d0de9d0-9b46-4f3a-b796-1ce3de01cf4c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e820b5d682a3ea5947d4811038d4a9bc5eaa38c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013923"
---
# <a name="single-sign-on-event-10665"></a>シングル サインオン: イベント 10665
## <a name="details"></a>詳細  

|                 |                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                               エンタープライズ シングル サインオン                                                |
| 製品バージョン |                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                               |
|    イベント ID     |                                                         10665                                                          |
|  イベント ソース   |                                                         ENTSSO                                                         |
|    コンポーネント    |                                                          N\A                                                           |
|  シンボル名  |                                                 SSO_WARN_NO_PROPERTIES                                                 |
|  メッセージ テキスト   | パスワード同期アダプターのプロパティを読み取り中のエラー。 既定値を使用しています。%r<br /><br /> アダプター: % 1 %r<br /><br /> エラー コード: %2 |

## <a name="explanation"></a>説明  
 この警告イベントは、既定のパスワード同期アダプターのプロパティの読み取り中にエラーが発生したことを示します。 各パスワード同期アダプターには、構成プロパティが関連付けられています。 これらのプロパティは SSO 構成ストアに格納されており、パスワード同期アダプターが作成されるときに、SSO コマンド ライン ツールまたは SSO 管理 MMC によって作成されます。  パスワード同期アダプターが他の方法で作成された場合、プロパティが不足している可能性があり、このエラーが発行される可能性があります。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解消するには、次の操作を行います:   

-   パスワード同期アダプターのプロパティを確認します。  

-   パスワード同期アダプターを再作成します。  

## <a name="more-info"></a>詳細

- **パスワード同期アダプターのプロパティ: オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]

- [パスワード同期](../core/password-synchronization2.md)
