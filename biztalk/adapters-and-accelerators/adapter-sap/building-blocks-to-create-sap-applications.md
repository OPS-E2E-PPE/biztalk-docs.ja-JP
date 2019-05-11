---
title: SAP アプリケーションを作成する構成要素 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- design-time tasks
- run-time tasks
- developing, fundamentals of (BizTalk applications)
ms.assetid: 591a5597-5e7d-44b0-8bee-e1c987c5e6c3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39e3b5aefa7a2f68945e300556d084fb2aed99dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373963"
---
# <a name="building-blocks-to-create-sap-applications"></a>SAP アプリケーションを作成する構成要素
使用して SAP システムの操作を実行する[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]アクティビティの 2 つのセットが含まれます: デザイン時および実行時のアクティビティ。 使用して、SAP システムの操作を実行する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を使用して、デザイン時および実行時のタスクのセットを実行する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]と[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールでそれぞれします。 このセクションでは、これらのタスクの概要を示します。 このセクションで例を使用して SAP システムで特定の操作を実行する方法を示すすべてのトピック[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、これらの高度なタスクをモデル化されます。  
  
## <a name="design-time-tasks"></a>デザイン時のタスク  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]参照、検索、および Rfc、Bapi、および使用して XML スキーマ定義言語 (Xsd) の形式で Idoc を SAP メタデータを取得する機能を提供、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。 Xsd は、SAP システムで実行する操作に固有と[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]は BizTalk プロジェクトを作成する場合にのみ使用できます。 デザイン時に、次のタスクを実行する必要があります。  
  
- **BizTalk プロジェクトを作成し、スキーマ生成**します。 最初に、Microsoft で BizTalk プロジェクトを作成する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]や、SAP システムの呼び出しは、RFC のスキーマを生成します。 たとえば、SAP システムで RFC_CUSTOMER_GET を呼び出す場合は、RFC_CUSTOMER_GET のメタデータを生成する必要があります。 この手順で使用して、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]スキーマを生成します。 詳細については、次を参照してください。 [Visual Studio で SAP 操作のメタデータの取得](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)します。  
  
- **オーケストレーションを設定**します。 スキーマを生成した後、オーケストレーション デザイナーを使用してオーケストレーションを設定する必要があります。 基本的なオーケストレーションには、受信と送信図形とし、受信論理ポートの送信を追加します。 後の手順では、BizTalk Server 管理コンソールを使用して物理ポートにこれらの論理ポートをマップします。 オーケストレーションでは、これらのポートを使用して、クライアントがアダプターから送信されるメッセージを選択します。 オーケストレーションは、SAP システムにメッセージを渡します。 SAP システムからの応答が受信されると、オーケストレーションは、アダプターのクライアントへの応答を渡します。  
  
- **メッセージを作成し、スキーマにリンク**します。 オーケストレーションでは、最初の手順で生成したスキーマにマップされるメッセージを作成する必要があります。 通常、要求メッセージと応答メッセージを作成します。 これらのメッセージは、対応する要求および応答スキーマにマップされます。  
  
- **メッセージとポートへのメッセージの構築図形のマップ**します。 オーケストレーションでは、3 番目の手順で作成したメッセージを 2 番目の手順で追加した各図形をマップする必要がありますようになりました。 そのメッセージを送信するポートをメッセージ図形をマップすることもあります。  
  
   たとえば、オーケストレーションの最初の図形がメッセージを受信する受信図形の場合は、要求メッセージと要求メッセージを送信するポートをこの図形をマップします。  
  
- **BizTalk プロジェクト ビルドおよび配置**します。 オーケストレーションを設定し、メッセージ、ポート、およびスキーマをマップした後は、BizTalk ソリューションをビルドする必要があります。 プロジェクトをビルドするため[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、アセンブリ キー ファイルは必要があります。 ソリューションを正常にビルドした後は、ソリューションを配置する必要があります。  
  
  > [!NOTE]
  >  手順についてを含め、これらの高度なタスクの詳細については、このセクションのさまざまなトピックで提供されます。  
  
  ソリューションをデプロイすると、デザイン時のタスクが実行されます。 実行時のタスクを実行する必要があります。  
  
## <a name="run-time-tasks"></a>実行時のタスク  
 実行時に、展開およびデザイン時に作成されたオーケストレーションを監視する、BizTalk Server 管理コンソールを使用できます。 さらに、する必要があります。  
  
- **アプリケーションを構成**します。 オーケストレーションとして、BizTalk Server 管理コンソールでデザイン時に展開した BizTalk プロジェクトが表示されます。 物理ポートを使用して今すぐ作成する必要がありますをデザイン時に作成した論理ポートをマッピングすることによって、このオーケストレーションを構成する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
   物理ポートでは、"action"または「アクション マッピング」を指定する必要があります。 このアクションは、SAP システムで実行する操作に対応します。 動的アクションを使用していない場合は、アクションを設定する必要があります。 
  
- **アプリケーションを起動**します。 アプリケーションを構成した後、アプリケーションを起動し、定義ファイルの場所で入力メッセージを削除する必要があります。 オーケストレーションは、入力メッセージを使用し、SAP システムに渡しますと応答を受信します。 この応答は別の定義済みのファイルの場所で使用可能になります。  
  
  これらの高度なデザイン時およびランタイム タスクを実現するには、その他のタスクを実行することも必要があります。 たとえば、使用、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]スキーマを生成するには、接続を SAP システムに接続するための URI を指定する必要があります。 このセクションでは情報などの反復的なタスクを使用して BizTalk アプリケーションの開発に実行する必要があります、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SAP アダプターを BizTalk Server 管理コンソールに追加します。](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)  
  
-   [SAP アダプターの接続 URI を構成します。](../../adapters-and-accelerators/adapter-sap/configure-the-connection-uri-for-the-sap-adapter.md)  
  
-   [SAP システムの資格情報で、サインオンを構成します。](../../adapters-and-accelerators/adapter-sap/configure-the-sign-in-credentials-for-the-sap-system.md) 
  
-   [SAP アダプターのバインドのプロパティを構成します。](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md)
  
-   [SAP システムの SOAP アクションを構成します。](../../adapters-and-accelerators/adapter-sap/configure-the-soap-action-for-the-sap-system.md)
  
-   [SAP アダプターを物理ポートのバインドを手動で構成します。](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)
  
-   [Sap ポートのバインド ファイルを使用して物理的なポート バインドを構成します。](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)
  
-   [SAP アダプターの動的ポートを構成します。](../../adapters-and-accelerators/adapter-sap/configure-dynamic-ports-in-the-sap-adapter.md)
  
-   [SAP アダプターのバインドを再利用します。](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)
  
## <a name="see-also"></a>参照  
[SAP アダプターを使用して BizTalk アプリケーションを開発する](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)