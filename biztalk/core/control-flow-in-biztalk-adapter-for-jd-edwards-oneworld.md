---
title: BizTalk adapter for JD Edwards OneWorld のフローの制御 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection pooling
- control flows
- apartment threading
- apartment threading, business functions
ms.assetid: 1ec865d0-2257-453b-9230-1f3787ebac38
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f6514a62a90fd2088c494ab2cc7384ceb0b59a9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354527"
---
# <a name="control-flow-in-biztalk-adapter-for-jd-edwards-oneworld"></a>BizTalk adapter for JD Edwards OneWorld の制御フロー
このトピックでは、JD Edwards OneWorld の Microsoft BizTalk Adapter のデザイン時および実行時の制御フローについて説明します。  
  
## <a name="design-time-flow"></a>デザイン時のフロー  
 アダプターでは、(トランスポートのプロパティ ダイアログ ボックスから、資格情報とシステム情報を使用) が開いたら、JD Edwards OneWorld アプリケーションのビジネス関数の 1 つまたは複数のインスタンスが作成され、プールされました。 アダプター ウィザードで、名前空間を参照するときは、ビジネス関数の一覧が表示されます。 ビジネス関数をクリックすると、メソッドの署名と共にその論理メソッドが表示されます。  
  
## <a name="run-time-flow"></a>実行時のフロー  
 JD Edwards OneWorld ビジネス関数のインスタンスが作成され、各スレッドのプールします。 JD Edwards OneWorld application ビジネス関数を使用して、メソッドのメタデータを読み取るメソッドの呼び出しがビジネス サービスに送信されると、ただし、メソッドのメタデータが既にキャッシュされている場合、ビジネス関数はキャッシュされた情報を使用し、適切なメソッドの呼び出しをします。 実行時に、JD Edwards OneWorld インターフェイス レイヤーが動的に構築されます。 インターフェイス レイヤーを通じては BizTalk Adapter for JD Edwards OneWorld は、呼び出しとデータ変換をサポートしています。  
  
 BizTalk Adapter for JD Edwards OneWorld では、BizTalk Server がこれらのインターフェイスの説明と対話することができるように、JD Edwards OneWorld アプリケーションのメソッド シグネチャにおけるインターフェイスの説明をマップします。  
  
 アダプターは、次の 1 つ以上の形式でアプリケーションの機能を拡張して、JD Edwards OneWorld アプリケーションとやり取りする企業のアプリケーションを有効にします。  
  
- ネイティブのデータ形式  
  
- 手順  
  
- メソッド  
  
- メッセージ  
  
- プロパティ  
  
- アプリケーション インターフェイス  
  
  実行時に、BizTalk Adapter for JD Edwards OneWorld は、JD Edwards OneWorld と対話するクライアント アプリケーション用のアプリケーション インターフェイスの説明を作成します。 アダプターは、作成、削除、および必要に応じて、アプリケーションで計算を実行し、直接メソッドを呼び出すには、ビジネス オブジェクトを呼び出すことができます。 JD Edwards OneWorld へのすべての呼び出しは、同期呼び出しです。 アダプターは、BizTalk Server から XML メッセージを受信し、SOAP エンベロープにメッセージを囲む、SOAP メッセージからの呼び出しのデータを Java の型に変換します。  
  
  次のようなプロセスのバックアップ、応答が送信されます。  
  
1.  Java の型は、SOAP メッセージに変換されます。  
  
2.  SOAP メッセージは、XML メッセージに変換されます。  
  
3.  XML メッセージは、さらに処理するため、BizTalk Server に送信されます。  
  
### <a name="apartment-threading-of-business-functions"></a>ビジネス関数のアパートメント スレッド  
 JD Edwards OneWorld のビジネス機能と任意のインスタンスは、作成、または取得されたスレッドでのみ使用できます。 これと呼ばれます*アパートメント スレッド*します。 BizTalk Adapter for JD Edwards OneWorld の接続プール フレームワークは、利用可能な接続のプールを管理します。  
  
### <a name="connection-pooling"></a>接続のプール  
 接続プールと、サーバー システムへの接続を開いたままにして、各呼び出しの後に終了するのではなく再利用することによって呼び出しのパフォーマンスが向上します。 BizTalk Adapter for JD Edwards OneWorld では、特定のログオン Id 内で接続をプールにできますが、すべてのプールの接続の合計数な制御を維持します。  
  
 新しいビジネス関数のすべてのインスタンスが作成され、各操作後に、インスタンスが破棄されるスレッドを使用します。 すべての JD Edwards OneWorld ビジネス関数呼び出しはステートレスです。ただし、時に、アダプターによりビジネス関数が正しいスレッドで使用されることです。  
  
## <a name="see-also"></a>参照  
 [アプリケーションの開発](../core/developing-applications3.md)   
 [計画および設計](../core/planning-and-architecture17.md)