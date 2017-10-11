---
title: "BizTalk Server プロジェクト内の WCF LOB Adapter SDK アダプターを使用する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 041f14cc-d00f-450d-b1e9-40a3e423c510
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84f81d23b56c2631879f366e6fe502840408a0d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="consume-a-wcf-lob-adapter-sdk-adapter-in-a-biztalk-server-project"></a>BizTalk Server プロジェクト内の WCF LOB Adapter SDK アダプターを使用します。
このトピックを使用して構築されたアダプターを使用する方法について説明、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]から[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を使用して、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]です。  
  
> [!NOTE]
>  使用するために、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、インストールする必要があります、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] 、同じホスト コンピューターでツール[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。  
  
 
## <a name="use-the-consume-adapter-service-add-in"></a>使用して、アダプターを使用する追加のサービス  
 
  
1.  .NET アプリケーションを開く[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。  
  
2.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]で、**プロジェクト** ウィンドウを右クリックし、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロジェクトをクリックして**追加**&#124;**生成された項目の追加**& #124 です。**アダプター サービスの使用**です。  
  
3.  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]画面で、アダプターのバインドを選択します。  
  
4.  をクリックして**構成**接続 URI、選択したアダプターのバインドを構成して、任意の資格情報、URI のプロパティ、およびバインドのプロパティを提供します。 実際の要件は、選択したアダプターのバインドによって異なります。  
  
5.  をクリックして**OK** URI を構成した場合。  
  
6.  **[接続]**をクリックします。 接続 URI が有効であり、クライアントの資格情報 (存在する場合) が受け入れられたら場合、**カテゴリ**ペインは、アダプターによって提供される操作とカテゴリで表示されます必要があります。  
  
7.  場合は、アダプターは、検索をサポート、検索フィールドはアクティブになります。 それ以外の場合、コントラクト型でフィルター処理および内のノードをクリックして、型および操作を探索できる、**カテゴリ**ウィンドウです。  
  
8.  をクリックして**OK**プロキシ成果物を生成します。 成果物の数は、コントラクトの型によって異なります。  
  
    |コントラクトの型|成果物|Description||  
    |-------------------|--------------|-----------------|-|  
    |送信|XML スキーマ|選択した種類および操作のスキーマが含まれています。||  
    |送信||Wcf-custom 送信ポートのバインド情報 XML|Wcf-custom 送信ポートの構成 XML が含まれています。|  
    |受信|XML スキーマ|選択した種類および操作のスキーマが含まれています。||  
    |受信||Wcf-custom 受信ポートのバインド情報 XML|Wcf-custom 受信ポートの構成 XML が含まれています。|  
  
9. 内の XML スキーマ ファイルを使えるようになりました、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションです。  
  
## <a name="deploy-the-biztalk-server-project"></a>BizTalk Server プロジェクトを配置します。  
  
1.  開いている**BizTalk Server 管理**です。  
  
2.  物理ポートを作成するには、ポートのバインド XML ファイルをインポートします。 対象のアプリケーションを右クリックし、**アプリケーション**グループで、**バインドのインポート**に移動して、適切なポートのバインド情報 XML ファイルを選択します。  
  
3.  定義されている論理ポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を新しく作成した物理ポートにオーケストレーションです。  
  
4.  をクリックして**オーケストレーション**、アプリケーションの下をクリックして、参加させ、オーケストレーションを右クリックして**Enlist**です。  
  
5.  をクリックして**オーケストレーション**、アプリケーションの下をクリックして、参加させ、オーケストレーションを右クリックして**開始**です。  
  
6.  右クリックし、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーション、およびクリック**開始**です。  
  
## <a name="generate-multiple-schemas"></a>複数のスキーマを生成します。  
 1 つまたは複数の要素をスキーマのコンパイル エラーが発生しました。 重複する可能性が複数のスキーマを生成するアダプター サービス使用ウィザードを使用する場合、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロジェクト。 選択してこれを回避する、**固有のスキーマ型の生成**一意の名前空間を持つスキーマ型が生成されるようにする チェック ボックスです。  
  
## <a name="see-also"></a>参照  
 [WCF LOB Adapter SDK を使用して作成されたアダプターを使用します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/consume-an-adapter-created-using-the-wcf-lob-adapter-sdk.md)