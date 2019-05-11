---
title: ビジュアルで Siebel システムに接続するアダプターを使用して Studio を使用して追加のサービス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2baaa361-1b14-4d00-bcef-f68bc3fa7139
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8d61bee08f59eb8fc48d989730e2cde053f0942
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371843"
---
# <a name="connect-to-the-siebel-system-in-visual-studio-using-consume-adapter-service-add-in"></a>ビジュアルで Siebel システムに接続するアダプターを使用して Studio を使用して追加のサービス
[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]をインストールするときにインストールされている[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]コンピューターにインストールされているすべての WCF カスタム バインドを読み込みます。 WCF ベースを使用して Siebel システムへの接続に[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]BizTalk プロジェクトで使用する必要があります、 **siebelBinding**します。  

## <a name="connecting-to-a-siebel-system-using-consume-adapter-service-add-in"></a>アダプターを使用してを使用して Siebel システムへの接続では、追加のサービス  
 使用して Siebel システムへの接続には、次の手順を実行、[!INCLUDE[consumeadapterservshort_md](../../includes/consumeadapterservshort-md.md)]します。  

#### <a name="to-connect-to-a-siebel-system"></a>Siebel システムに接続するには  

1. 使用して接続する、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] BizTalk ソリューションで。  

   1. 使用して BizTalk プロジェクトを作成する[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。  

   2. ソリューション エクスプ ローラーでプロジェクトを右クリックし、**追加** をクリックし、**生成した項目の追加**します。  

   3. **生成した項目の追加** ダイアログ ボックスで、次の操作を行います。  


      |    プロパティ    |             目的             |
      |----------------|------------------------------------|
      | **カテゴリ** | クリックして**アダプター サービスの使用**します。 |
      | **[テンプレート]**  | クリックして**アダプター サービスの使用**します。 |


   4. **[追加]** をクリックします。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] が表示されます。  

2. **バインディングを選択**ドロップダウン リスト、選択**siebelBinding**、 をクリックし、**構成**します。  

3. **アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**.  

4. ユーザー名と Siebel システムへの接続にパスワードを指定します。  

5. をクリックして、 **URI プロパティ**タブをクリックし、接続パラメーターの値を指定します。 接続 URI の詳細についてはの[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[Siebel システム接続 URI の作成](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)です。  

   > [!NOTE]
   >  接続パラメーターに予約済みの文字が含まれている場合、としてを指定する必要がありますのでは、 **URI プロパティ**タブ、つまり、エスケープ文字を使用せずします。 ただし、直接の URI を指定する場合、 **URI の構成**フィールドと接続パラメーターは、予約文字を含めることが、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。  

6. をクリックして、**バインド プロパティ**タブをクリックし、対象と操作に必要な場合、バインドのプロパティの値を指定します。 バインド プロパティの詳細については、次を参照してください。 [for Siebel のバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)します。  

7. **[OK]** をクリックします。  

8. **[接続]** をクリックします。 として、接続の状態が示すように、接続が確立されると、**接続**します。  

    次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]接続が確立された後すぐにします。  

    ![アダプター サービスの使用 ダイアログ ボックスの接続](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-01-connected.gif "SIEBEL-ADPT-Lesson1-Step3-01-connected")  

    [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] Siebel システムで実行できるさまざまな操作を含む別のノードが表示されます。 たとえば、**ビジネス オブジェクト**ノードには、すべてのビジネス オブジェクトと Siebel システムで呼び出すことができるビジネス コンポーネントが含まれています。 同様に、**ビジネス サービス**ノードには、すべてのビジネス サービスに接続されている Siebel システムが含まれています。 これらのノードの詳細については、次を参照してください。[メタデータ ノード Id](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md)します。