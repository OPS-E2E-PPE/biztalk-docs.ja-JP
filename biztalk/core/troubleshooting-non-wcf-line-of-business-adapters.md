---
title: WCF 以外の行のビジネスのアダプターのトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d5f7877-656f-406e-9edb-d6b9a0705b02
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6c5e9b2ffe7e74fc7bf14c3d14a22a93e288b30
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997051"
---
# <a name="troubleshooting-non-wcf-line-of-business-adapters"></a>WCF 以外の基幹業務アダプターのトラブルシューティング
## <a name="failed-to-retrieve-error"></a>''取得できませんでした" エラー  
 WCF 以外の基幹業務 (LOB) アダプターを使用する場合、次のエラーが発生することがあります。  
  
-   システムを取得できませんでした  
  
-   ブラウジング エージェント: エラーは、コンストラクターにトラップされました。 ターゲット マシンは能動的に接続を拒否しました。  
  
-   ランタイム エージェント: エラーは、コンストラクターにトラップされました。 ターゲット マシンは能動的に接続を拒否しました。  
  
### <a name="cause"></a>原因  
 基幹業務 (LOB) アダプターが .Net リモート処理を使用しています。 .Net リモート処理のライセンス認証に予想より時間がかかる場合、アダプターがこれらのエラーを返していることがあります。  
  
### <a name="resolution"></a>解決策  
 作成、 **StartAgentSleep**レジストリ キーとタイムアウト値を大きくします。  
  
1. レジストリを開きに移動*hkey_local_machine \software\microsoft\biztalkadapters*します。  
  
2. 次のプロパティで新しい DWORD 値を作成します。  
  
    名前: StartAgentSleep  
  
    基本: 10 進数  
  
    データの値: 1000  
  
   値のデータはミリ秒 (ms) 単位で指定します。 1000ms が 1 秒です。  
  
   一部のシステムでは 1 秒では足りない可能性があります。 値を大きくし、テストして妥当なタイムアウトかどうか判断します。  
  
> [!IMPORTANT]
>  追加、 **StartAgentSleep**レジストリ キーへの影響**すべて**非 WCF LOB アダプター。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server アダプターのトラブルシューティング](../core/troubleshooting-biztalk-server-adapters.md)