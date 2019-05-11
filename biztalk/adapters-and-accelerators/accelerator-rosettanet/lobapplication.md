---
title: LOBApplication |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- trading partners, submitting actions
- LOBs, submitting actions
- LOBApplication utility
- trading partners, response messages
- LOBs, LOBApplication utility
- LOBs, response messages
ms.assetid: ad5986af-4175-49cd-806b-04e1fde63f55
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3f65980015d689cd79f1d006441c1687d15be01
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283328"
---
# <a name="lobapplication"></a>LOBApplication
実際の基幹業務 (LOB) デスクトップ プログラムをシミュレートする取引先のアクションまたは応答メッセージを送信するのにには、LOBApplication ユーティリティを使用します。  
  
 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]サンプル メッセージを提供します、 \<*ドライブ*\>\Program Files (x86) \Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\LOBApplication\SampleInstances フォルダーです。  
  
## <a name="location-in-sdk"></a>SDK でのパス  
 \<*ドライブ*\>\Program Files (x86) \Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\lobapplication  
  
## <a name="running-lobapplication"></a>LOBApplication の実行  
  
#### <a name="to-run-lobapplication"></a>LOBApplication を実行するには  
  
1.  Windows エクスプ ローラーで、移動\<*ドライブ*\>\Program Files (x86) \Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\\します。  
  
2.  ダブルクリック**LOBApplication.exe**、し、ENTER キーを押します。  
  
     次のページでは、ユーティリティを実行するために必要な情報の表示します。  
  
## <a name="syntax-for-lobapplication"></a>LOBApplication の構文  
 使用して、 **LOB Application**ページをホームとパートナーの名前、プロセス PIP (Partner Interface) のプロパティ、および LOBApplication ユーティリティによって送信されたメッセージのメッセージのプロパティを指定します。  
  
 次の表に、各フィールドの使用方法、 **LOB Application**ページ。  
  
|プロパティ|目的|  
|--------------|----------------|  
|**Home Profile Name**|ホーム組織 (送信元パーティ) の名前を入力します。|  
|**取引先名**|取引先 (送信先パーティ) の名前を入力します。|  
|**PIP の名前**|入力の種類」などの PIP 表示コード**3 a 2**します。 この値は、大文字と小文字が区別されます。|  
|**[PIP Version]**|入力の種類」などの PIP のバージョン**V02.00**します。 この値は、大文字と小文字が区別されます。|  
|**PIP インスタンス ID** (省略可能)|たとえば、入力、PIP の英数字のインスタンス ID を入力**STD_3A2_V02.02**します。 特殊文字を避けてください。 ID は、取引先および PIP コードごとに一意である必要があります。 LOBApplication ユーティリティはメッセージとしてマークされているアクションのメッセージ場合は、インスタンス ID は空の場合、PIP インスタンス id、生成された HUID 値を使用してください。 **注:** 選択すると**応答**で、**メッセージ カテゴリ**、PIP インスタンス ID は、このフィールドに入力する必要があります。|  
|**[ファイル名]**|省略記号ボタン (…) をクリックして、PIP インスタンス ファイルを含むフォルダーに移動し、PIP インスタンス ファイルをクリックします。|  
|**メッセージのカテゴリ**|メッセージの種類を選択します (**アクション**または**応答**)。|  
|**[Attachments]**|クリックして**追加**、添付ファイルを含むフォルダーに移動し、クリックして**オープン**します。|  
|**メッセージを送信します。**|メッセージを送信する をクリックします。|  
|**ステータス**|このフィールド内のアクションの状態を読み取ります。|  
  
## <a name="remarks"></a>コメント  
 LOBApplication ユーティリティは、指定すると、プロパティを持つメッセージを作成し、取引先パートナーに送信します。 このユーティリティは、メッセージの service content データを BTARNDATA データベースの MessageFromLOB テーブルに書き込みます。 このユーティリティは、アクション メッセージの送信をシミュレートします。  
  
 LOBApplication フォルダー下の SampleInstances フォルダーにサンプル メッセージ、 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK は次のグローバル ビジネス識別子 (Gbi) と仮定する事前構成済み。ホーム組織とパートナー組織に対して 987654321 123456789 します。 以外の Gbi を使用するテキスト エディターで、サンプル メッセージを変更する必要があります。  
  
 メッセージを送信する基幹業務デスクトップ プログラムをシミュレートするのにには、LOBApplication ユーティリティを使用します。 LOBWebApplication ユーティリティは、メッセージを送信する基幹業務 (LOB) Web アプリケーションをシミュレートするために使用します。  
  
## <a name="see-also"></a>参照  
 [ユーティリティ](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)   
 [LOBWebApplication](../../adapters-and-accelerators/accelerator-rosettanet/lobwebapplication.md)
