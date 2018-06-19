---
title: 'シングル サインオン: イベント 10748 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b4b18ea-6565-4c0b-89f8-30a8c67601ba
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d83f0bfec0137e0788b55ca6aa5857f3dcfcc50
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276506"
---
# <a name="single-sign-on-event-10748"></a>シングル サインオン: イベント 10748
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10748|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_WARN_PS_ADAPTER_NOT_RUNNING|  
|メッセージ テキスト|接続先アダプターに接続できませんでした。<br /><br /> 実行されていないか、初期化されていない可能性があります。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: %2 %r<br /><br /> SSO サーバー名: %3 %r<br /><br /> エラー コード: %4|  
  
## <a name="explanation"></a>説明  
 この警告イベントは、パスワード同期で、指定されたパスワード同期アダプターに接続できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 この警告を解消するには、次の操作を行います:   
  
-   外部アダプターを確認します。  
  
-   MMC スナップインまたはコマンド ライン ツールを使用してアダプターを有効にします。  
  
-   関連するエラーについては、システムおよびアプリケーションのイベント ログを確認します。  
  
 詳細については、次のリソースを参照してください。  
  
-   [パスワード同期を管理する方法](../core/how-to-administer-password-synchronization.md)