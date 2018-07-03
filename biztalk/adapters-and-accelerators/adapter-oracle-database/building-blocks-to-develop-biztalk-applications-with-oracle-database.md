---
title: Oracle データベースと BizTalk アプリケーションを開発する構成要素 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- developing, BizTalk applications
- run-time tasks
- design-time tasks
ms.assetid: ad9ca856-5569-41ab-8617-ae6db5e3b4d7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 703bff35321fcedb4240d8ced1f422707c0ca51e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973803"
---
# <a name="building-blocks-to-develop-biztalk-applications-with-oracle-database"></a>Oracle データベースと BizTalk アプリケーションを開発する構成要素
使用して Oracle データベースに対する操作の実行、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]タスクの 2 つのセットが含まれます: デザイン時および実行時。  
  
## <a name="design-time-tasks"></a>デザイン時のタスク  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]参照、検索、およびを使用して Oracle メタデータ テーブル、ストアド プロシージャ、および XML スキーマ定義言語 (Xsd) の形式でこのようなその他の項目を取得する機能を提供、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]します。 Xsd では、Oracle データベースで実行する操作に固有です。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]は BizTalk プロジェクトを作成する場合にのみ使用できます。 デザイン時に、次のタスクを実行する必要があります。  
  
- **BizTalk プロジェクトを作成し、スキーマ生成**します。 Microsoft で BizTalk プロジェクトを作成する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]と Oracle データベースで実行される操作のスキーマを生成します。 たとえば、EMPLOYEE テーブルにレコードを挿入する場合は、EMPLOYEE テーブルに対して挿入操作のメタデータを生成する必要があります。 この手順で使用して、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]スキーマを生成します。 詳細については、次を参照してください。 [Visual Studio での Oracle データベース操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)します。
  
- **オーケストレーションを設定**します。 スキーマを生成した後、オーケストレーション デザイナーを使用してオーケストレーションを設定する必要があります。 基本的なオーケストレーションには、受信と送信図形とし、受信論理ポートの送信を追加します。 後の手順では、BizTalk Server 管理コンソールを使用して物理ポートにこれらの論理ポートをマップします。 オーケストレーションでは、これらのポートを使用して、クライアントがアダプターから送信されるメッセージを選択します。 オーケストレーションは、Oracle データベースにメッセージを渡します。 Oracle データベースからの応答が受信されると、オーケストレーションは、アダプターのクライアントへの応答を渡します。  
  
- **メッセージを作成し、スキーマにリンク**します。 オーケストレーションでは、最初の手順で生成したスキーマにマップされるメッセージを作成する必要があります。 通常、要求メッセージと応答メッセージを作成します。 これらのメッセージは、対応する要求および応答スキーマにマップされます。  
  
- **メッセージとポートへのメッセージの構築図形のマップ**します。 オーケストレーションでは、3 番目の手順で作成したメッセージを 2 番目の手順で追加した各図形をマップする必要がありますようになりました。 そのメッセージを送信するポートをメッセージ図形をマップすることもあります。  
  
   たとえば、オーケストレーションの最初の図形がメッセージを受信する受信図形の場合は、要求メッセージと要求メッセージを送信するポートをこの図形をマップします。  
  
- **BizTalk プロジェクト ビルドおよび配置**します。 オーケストレーションとマップされたメッセージ、ポート、およびスキーマを設定した後は、BizTalk ソリューションをビルドする必要があります。 プロジェクトをビルドするため[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、アセンブリ キー ファイルを作成する必要があります。 ソリューションを正常にビルドした後は、ソリューションを配置する必要があります。  
  
  > [!NOTE]
  >  手順についてを含め、これらの高度なタスクの詳細については、このセクションのさまざまなトピックで提供されます。  
  
  ソリューションをデプロイすると、デザイン時のタスクが実行されます。 実行時のタスクを実行する必要があります。  
  
## <a name="run-time-tasks"></a>実行時のタスク  
 実行時に、展開およびデザイン時に作成されたオーケストレーションを監視する、BizTalk Server 管理コンソールを使用できます。 さらに、する必要があります。  
  
- **アプリケーションを構成**します。 オーケストレーションとして、BizTalk Server 管理コンソールでデザイン時に展開した BizTalk プロジェクトが表示されます。 BizTalk Server 管理コンソールを使用して今すぐ作成する必要がある物理ポートにデザイン時に作成した論理ポートをマッピングすることによって、このオーケストレーションを構成する必要があります。  
  
   物理ポートでは、"action"または「アクション マッピング」を指定する必要があります。 このアクションは、Oracle データベースで実行する操作に対応します。 動的アクションを使用していない場合は、アクションを設定する必要があります。  
  
- **アプリケーションを起動**します。 アプリケーションを構成した後、アプリケーションを起動し、定義ファイルの場所で入力メッセージを削除する必要があります。 オーケストレーションは、入力メッセージを使用し、Oracle データベースに渡しますと応答を受信します。 この応答は別の定義済みのファイルの場所で使用可能になります。  
  
  これらの高度なデザイン時およびランタイム タスクを実現するには、その他のタスクを実行することも必要があります。 たとえば、使用、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]スキーマを生成するには、接続を Oracle データベースに接続するための URI を指定する必要があります。 このセクションでは情報などの反復的なタスクを使用して BizTalk アプリケーションの開発に実行する必要があります、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  

  
## <a name="see-also"></a>参照  
[Oracle データベース アダプターを使用して BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-biztalk-applications-using-the-oracle-database-adapter.md)