---
title: BizTalk Server プロジェクト内の WCF LOB Adapter SDK のアダプターの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 041f14cc-d00f-450d-b1e9-40a3e423c510
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0ad9b2659ce20876807d894f99751eeb265e92e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363825"
---
# <a name="consume-a-wcf-lob-adapter-sdk-adapter-in-a-biztalk-server-project"></a>BizTalk Server プロジェクト内の WCF LOB Adapter SDK のアダプターを使用します。
このトピックを使用して構築されたアダプターを使用する方法を説明します、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]から[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を使用して、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]します。  

> [!NOTE]
>  使用するには、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、インストールする必要があります、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ホストと同じコンピューターでツール[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。  


## <a name="use-the-consume-adapter-service-add-in"></a>使用して、アダプターを使用する追加のサービス  


1. .NET アプリケーションを開く[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。  

2. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]で、**プロジェクト** ウィンドウを右クリックし、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロジェクトをクリックして**追加**&#124;**生成された項目の追加**&#124; です。**アダプター サービスの使用**です。  

3. [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]画面で、アダプターのバインドを選択します。  

4. クリックして**構成**接続 URI の選択したアダプターのバインドを構成し、任意の資格情報、URI のプロパティ、およびバインドのプロパティを提供します。 実際の要件は、選択したアダプターのバインドによって異なります。  

5. クリックして**OK** URI を構成するときにします。  

6. **[接続]** をクリックします。 接続 URI が有効であり (あれば) のクライアント資格情報が受け入れられたら場合、**カテゴリ**ウィンドウ、カテゴリと、アダプターによって提供される操作を入力します。  

7. アダプターは、検索をサポート、検索フィールドがアクティブになります。 それ以外の場合、コントラクト型でフィルター処理および内のノードをクリックして、型と操作を探索できる、**カテゴリ**ウィンドウ。  

8. クリックして**OK**プロキシ成果物を生成します。 成果物の数は、コントラクトの型によって異なります。  


   | コントラクト型 |  成果物   |                         説明                         |                                                             |
   |---------------|-------------|-------------------------------------------------------------|-------------------------------------------------------------|
   |   送信    | XML スキーマ | 選択した型と操作のスキーマが含まれています。 |                                                             |
   |   送信    |             |        Wcf-custom 送信ポートのバインド情報 XML         |  Wcf-custom 送信ポートの構成 XML が含まれています。   |
   |    受信    | XML スキーマ | 選択した型と操作のスキーマが含まれています。 |                                                             |
   |    受信    |             |       Wcf-custom 受信ポートのバインド情報 XML       | Wcf-custom の受信ポートの構成 XML が含まれています。 |


9. 内の XML スキーマ ファイルを使用できます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーション。  

## <a name="deploy-the-biztalk-server-project"></a>BizTalk Server プロジェクトを配置します。  

1. 開いている**BizTalk Server 管理**します。  

2. 物理ポートを作成するには、ポートのバインド XML ファイルをインポートします。 対象のアプリケーションを右クリックし、**アプリケーション**グループで、**バインドのインポート**に移動して、適切なポートのバインド情報 XML ファイルを選択します。  

3. 定義されている論理ポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を新しく作成された物理ポートにオーケストレーションします。  

4. クリックして**オーケストレーション**、アプリケーションでは、下をクリックして、参加させ、オーケストレーションを右クリックして**参加**します。  

5. クリックして**オーケストレーション**、アプリケーションでは、下をクリックして、参加させ、オーケストレーションを右クリックして**開始**します。  

6. 右クリックし、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーション、およびクリック**開始**します。  

## <a name="generate-multiple-schemas"></a>複数のスキーマを生成します。  
 1 つまたは複数の要素をスキーマのコンパイル エラーが発生しました。 重複する可能性が複数のスキーマを生成するアダプター サービス使用ウィザードを使用する場合、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロジェクト。 選択してこれを回避する、**一意のスキーマ型の生成**一意の名前空間を持つスキーマ型が生成されることを確認する チェック ボックス。  

## <a name="see-also"></a>参照  
 [WCF LOB Adapter SDK を使用して作成されたアダプタを使用します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/consume-an-adapter-created-using-the-wcf-lob-adapter-sdk.md)