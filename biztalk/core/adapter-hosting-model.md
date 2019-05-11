---
title: アダプターのホスト モデル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf9a8e6b-8c8d-47ec-b2a3-aed58206121d
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f6603c07bc74cb904ad3eb88f50a3c7d2c60d09
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361427"
---
# <a name="adapter-hosting-model"></a>アダプターのホスト モデル
一般に BizTalk アダプターは、BizTalk サービス Btsntsvc.exe でホストされます。 つまり、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アダプターの有効期間を管理します。 場合、次のように、他のプロセスの管理対象アダプター。  
  
## <a name="in-process-adapters"></a>インプロセス アダプター  
 管理されているアダプター[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インプロセス アダプターと呼ばれます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] これらのアダプターは、次を行います。  
  
- アダプターをインスタンス化時に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が開始  
  
- 初期化中に、アダプターのトランスポート プロキシをアダプターに渡します  
  
- サービスのアダプターの要求  
  
- アダプターのシャット ダウンを終了します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サービス  
  
  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 実行時に、アダプター ハンドラーの構成およびエンドポイントの構成情報を提供します。 アクティブに要求を処理するために、アダプターが有効なを特定の期間を定義する windows サービスなど、他の構成が指定されます。  
  
  BizTalk サービスが手動でシャット ダウンを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールまたはサービス コントロール マネージャーを使用しています。 場合への接続、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースには、サービスが失われることに自動的に自体をリサイクルします。  
  
  一般的なホスティング モデルでは、受信側アダプターと送信側アダプターがメッセージング エンジンとオーケストレーション エンジンと共に、BizTalk サービスと同じプロセスでホストされます。 ホスティング モデルは、受信、送信、およびオーケストレーションのホストとこれらの組み合わせの分離を許可するのに十分な柔軟性があります。 次の図では、ホストは同じプロセス内で 3 つすべてを実行しています。  
  
  リッチのホスティング モデルであるため重要な点に注意するアダプターの送信を開発するときに、受信アダプターと同じホストで構成できない可能性があります。 また、別のコンピューターで実行するでも構成できます。  
  
  ![](../core/media/regularadapterhostingmodel.gif "RegularAdapterHostingModel")  
  インプロセス アダプターのホスト モデル  
  
## <a name="isolated-adapters"></a>分離アダプター  
 BizTalk サービスで受信アダプターをホストしているときにシナリオのことはできません。 たとえば、インターネット インフォメーション サービス (IIS) プロセス モデルは、IIS で ASP.NET アプリケーションと ISAPI 拡張機能の有効期間管理されるようは。 BizTalk SOAP アダプターは、IIS と同じプロセス領域内で実行する必要がありますできなくなり[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SOAP アダプターのすべてのインスタンスの有効期間を制御します。  
  
 これらの種類のアダプターの分離受信アダプター、または単に分離アダプターと呼ばれるもう 1 つのホスティング モデルがあります。 分離送信アダプターの概念はありません。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]分離アダプターを作成することはできません、アダプターのトランスポート プロキシを取得し、そのトランスポート プロキシで自身を登録する必要があります。  
  
 次の図を示しています、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アーキテクチャをホストします。 パフォーマンスを低下させない分離ホスト アーキテクチャは、不要なプロセス間通信を除去しようとします。 分離アダプターと BizTalk メッセージング エンジン スタックは、同じプロセスでは、ためはプロセス間通信、アダプターがメッセージング エンジンを呼び出すときに、 シナリオでは、メッセージング エンジンとデータベース間の唯一のプロセス間通信は、これは回避できません。  
  
 ![](../core/media/isolatedadapters.gif "IsolatedAdapters")  
分離アダプターのホスティング モデル  
  
## <a name="see-also"></a>参照  
 [アダプター フレームワークについて](../core/what-is-the-adapter-framework.md)