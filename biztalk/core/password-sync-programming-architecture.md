---
title: パスワード同期のプログラミング アーキテクチャ |Microsoft Docs
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
ms.openlocfilehash: 9da005574ef041eaa20582d02d1affd196963c81
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394989"
---
# <a name="password-sync-programming-architecture"></a>パスワード同期のプログラミング アーキテクチャ
パスワード同期アダプターが、エンタープライズ シングル サインオン システムの残りの部分と対話するためのプル モデルを使用します。 つまり、アクティブに受信パスワードの変更、エンタープライズ シングル サインオン (ENTSSO) サービスおよび Windows 以外のシステムからも。 同様に、アダプターは、他の 1 つのシステムから受信したパスワードの変更をプッシュします。 このモデルでは、アダプターが次の 3 つのアーキテクチャのコンポーネントと対話: ENTSSO アーキテクチャ、パスワード同期 (PS) ヘルパー コンポーネント、および非 Windows システムを指定します。  
  
## <a name="enterprise-single-sign-on-architecture"></a>エンタープライズ シングル サインオンのアーキテクチャ  
 ENTSSO は、エンタープライズ シングル サインオン テクノロジを実装し、アダプターと同じシステム上でローカル サービスとして実行するサービスです。 そのため、アダプターと ENTSSO 間の通信では、常にローカルです。 ただし、パスワード同期アダプターは ENTSSO サービスから別のプロセスで実行されます。  
  
 ENTSSO では、構成ストアを使用して、アダプターの構成情報を格納します。 構成ストアのアプリケーションのアプリケーション ユーザー アカウントは、アクセス アカウントに対応します。 アダプターが ENTSSO を呼び出す、ENTSSO では、アダプターがそのアダプターの構成済みのアクセス アカウント内にあるによって確認されます。 アクセス アカウントは、(ローカルまたはドメイン) のグループ アカウントである必要があります。  
  
 ENTSSO では、アダプターに関する情報を格納、ため、アダプター自体を識別できます ENTSSO によってそのアダプターの名前。 アダプター名は、構成ストアのアプリケーション名とアダプターのプロパティを格納するために使用する構成ストア識別子に対応します。 そのため、アダプターはアダプター名の構成情報にアクセスして、正しく実行時に、ENTSSO システムを識別が必要です。  
  
## <a name="password-sync-helper"></a>パスワード同期ヘルパー  
 パスワード同期 (PS) ヘルパーは、ENTSSO によって提供される COM コンポーネントです。 PS ヘルパーでインプロセスで動作をパスワード同期アダプターと ISSOPSWrapper を公開します。 アダプターは、ENTSSO サービスと通信するいずれかのインターフェイスを呼び出すことができます。 ENTSSO を使用してとは、PS ヘルパー パスの通信には、(パケット プライバシー) 軽量のリモート プロシージャ コール (LRPC) が暗号化されます。 通信は、主にパスワードの更新は、アダプターと ENTSSO の間の他の種類の通知を渡すインターフェイスを使用することもできます。 PS ヘルパーは、プロセスごとのシングルトン値として実行するためには、複数のアダプターが同じアダプター プロセス内から同じ PS ヘルパー オブジェクトを呼び出す可能性があります。 プログラムによる PS ヘルパーの使用に関する詳細については、次を参照してください。[パスワードを同期](../core/synchronizing-passwords.md)します。  
  
## <a name="non-windows-system"></a>非 Windows システム  
 非 Windows システムは、アダプターと対話するリモート コンピューターです。 非 Windows システムと対話する方法は自由です。  
  
## <a name="see-also"></a>参照  
 [パスワード同期アダプター](../core/password-sync-adapters.md)