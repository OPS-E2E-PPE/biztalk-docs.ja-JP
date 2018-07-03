---
title: SQL に接続する Visual Studio を使用してサーバー プラグインのアダプター サービス参照の追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fc3b824-d20b-4531-81f3-89b4a1ff3216
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9998acf89bd036230dceb3a06f950497677490b9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018264"
---
# <a name="connect-to-sql-server-in-visual-studio-using-add-adapter-service-reference-plug-in"></a>SQL に接続する Visual Studio を使用してサーバー プラグインのアダプター サービス参照の追加
使用して SQL Server に接続するため、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] .NET プログラミング ソリューションでは、使用する必要があります、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]します。 このトピックでは、手順を使用する方法には、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  

## <a name="connecting-to-sql-server-using-add-adapter-service-reference-plug-in"></a>SQL に接続するサーバーを使用して、アダプター サービス参照のプラグインを追加  
 SQL Server に接続するのには、次の手順を実行、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  

#### <a name="to-connect-to-sql-server"></a>SQL Server に接続するには  

1. 使用して接続する、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]プログラミング ソリューション。  

   1. プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。  

   2. ソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックし、**アダプター サービス参照の追加**します。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] が表示されます。  

2. **バインディングを選択**ドロップダウン リスト、選択**sqlBinding**、 をクリックし、**構成**します。  

3. **アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リストで、次のいずれかの操作を行います。  

   > [!NOTE]
   >  」の説明に従って、ログインしているが、Windows ユーザーを SQL Server に追加する必要があります Windows 認証を使用して SQL Server に接続する場合[SQL アダプターを使用した Windows 認証を使用して SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)します。  

   |  このボタンをクリックします。  |                                                                                                                                                               目的                                                                                                                                                               |
   |--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |   **なし**   |                                                                                                                                         Windows 認証を使用して、SQL Server に接続します。                                                                                                                                         |
   | **Windows**  |                                                                                                                                         Windows 認証を使用して、SQL Server に接続します。                                                                                                                                         |
   | **ユーザー名** | ユーザー名とパスワードを指定し、SQL Server データベースで定義されているユーザーの資格情報を指定して SQL Server に接続します。 ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。 **注:** のままにする場合、**ユーザー名**と**パスワード**フィールドを空白、アダプターが Windows 認証を使用して SQL Server に接続します。 |


4. をクリックして、 **URI プロパティ**タブをクリックし、接続パラメーターの値を指定します。 接続 URI の詳細についてはの[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[SQL Server 接続 URI の作成](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。  

   > [!NOTE]
   >  接続パラメーターに予約済みの文字が含まれている場合、としてを指定する必要がありますのでは、 **URI プロパティ**タブ、つまり、エスケープ文字を使用せずします。 ただし、直接の URI を指定する場合、 **URI の構成**フィールドと接続パラメーターは、予約文字を含めることが、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。  
   > 
   > [!NOTE]
   >  [URI のプロパティ] タブで値を指定しないと、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] により URI が `mssql://.//` になります。 このような場合、アダプターは既定のデータベースと、ローカル コンピューター上の既定のデータベース インスタンスに接続します。  

5. をクリックして、**バインド プロパティ**タブをクリックし、対象と操作に必要な場合、バインドのプロパティの値を指定します。  

6. **[OK]** をクリックします。  

7. **[接続]** をクリックします。 接続が確立されると、接続の状態が表示として**接続**します。  

    次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]接続が確立された後すぐにします。 グラフィカル ユーザー インターフェイスは変わりません、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  

    ![SQL Server に接続](../../adapters-and-accelerators/adapter-sql/media/661adb8a-5050-44d5-8db8-fdf0fe530b40.gif "661adb8a-5050-44d5-8db8-fdf0fe530b40")  

    [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] SQL Server で実行できるさまざまな操作を含む別のノードが表示されます。 たとえば、**プロシージャ**ノードに接続されているデータベースに使用できるすべてのプロシージャが含まれています。 同様に、**テーブル**ノードに接続して、データベースとテーブルで実行できる操作のすべてのテーブルが含まれています。 これらのノードの詳細については、次を参照してください。[メタデータ ノード Id](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md)します。  

## <a name="see-also"></a>参照  
 [Consume Adapter Service アドインを使用して Visual Studio での SQL Server に接続します。](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)