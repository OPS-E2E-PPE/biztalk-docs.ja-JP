---
title: パスワード同期のプログラミング アーキテクチャ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 679edbf1-fb08-4472-b366-3e1d361b20e7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebb68af3624b19a5a5385902d6a0131cfe28acb8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264674"
---
# <a name="password-sync-programming-architecture"></a>パスワード同期のプログラミング アーキテクチャ
パスワード同期アダプターが、エンタープライズ シングル サインオン システムの残りの部分と対話するためにプル モデルを使用します。 つまり、アクティブに受信パスワードの変更、エンタープライズ シングル サインオン (ENTSSO) サービスおよび Windows 以外のシステムからもします。 同様に、このアダプターは、あるシステムから別のシステムへ受け取ったパスワードの変更をプッシュします。 このモデルで、アダプターと連携 3 つのアーキテクチャ コンポーネント: ENTSSO アーキテクチャ、パスワード同期 (PS) ヘルパー コンポーネント、および指定した非 Windows システムです。  
  
## <a name="enterprise-single-sign-on-architecture"></a>エンタープライズ シングル サインオンのアーキテクチャ  
 ENTSSO は、エンタープライズ シングル サインオン機能を実装しているサービスです。このサービスは、アダプターと同じシステムでローカル サービスとして実行されます。 このため、アダプターと ENTSSO との通信が常にローカルになります。 ただし、パスワード同期アダプターは、ENTSSO サービスとは別のプロセスで実行されます。  
  
 ENTSSO は、構成ストアを使用して、アダプターの構成情報を格納します。 構成ストア アプリケーションのアプリケーション ユーザー アカウントは、アクセス アカウントに対応します。 アダプターが ENTSSO を呼び出すと、ENTSSO は、アダプターが構成されたアクセス アカウントの範囲内であることを確認します。 アクセス アカウントは、(ローカルまたはドメイン) グループ アカウントにする必要があります。  
  
 ENTSSO では、アダプターに関する情報が格納されるため、アダプターは、アダプター名を使用してアダプター自体を識別できます。 アダプター名は、構成ストア アプリケーション名、およびアダプター プロパティの格納に使用される構成ストア識別子に対応しています。 したがって、構成情報にアクセスし、実行時の ENTSSO システムでアダプター自体の識別を正確に行う場合には、アダプターはアダプター名を認識する必要があります。  
  
## <a name="password-sync-helper"></a>パスワード同期ヘルパー  
 パスワード同期 (PS) ヘルパーは、ENTSSO によって提供される COM コンポーネントです。 PS ヘルパーは、パスワード同期アダプターと一緒にインプロセスで実行されます。また、ISSOPSWrapper を公開します。 アダプターは、ENTSSO サービスと通信するために、いずれかのインターフェイスを呼び出すことができます。 PS ヘルパーは、暗号化された (パケット プライバシー) LRPC (Lightweight Remote Procedure Call) を使用して、ENTSSO と通信します。 通信は主にパスワードの更新を目的としていますが、インターフェイスを使用して、他の種類の通知をアダプターと ENTSSO 間で渡すこともできます。 PS ヘルパーはプロセスごとに単一の値として実行されるので、複数のアダプターが同じアダプター プロセスから同じ PS ヘルパー オブジェクトを呼び出すことができます。 プログラムによる PS ヘルパーの使用の詳細については、次を参照してください。[パスワードを同期する](../core/synchronizing-passwords.md)です。  
  
## <a name="non-windows-system"></a>Windows 以外のシステム  
 Windows 以外のシステムとは、アダプターと連携するリモート コンピューターです。 Windows 以外のシステムとの連携方法は、ユーザーが決定します。  
  
## <a name="see-also"></a>参照  
 [パスワード同期アダプター](../core/password-sync-adapters.md)